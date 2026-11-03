---
repo: autoluga
name: nahradni-dily
type: quick_fix
tool: claude-code
---

# Náhradní dily

Kontext
Projekt: /var/www/autoluga.cz/autoluga (Bolt CMS 6 / Symfony, téma public/theme/autoluga, Vite build v assets/). Nejdřív si přečti CLAUDE.md a dodržuj ho: všechny identifikátory anglicky (soubory, Twig, proměnné, třídy, ID, klíče configu, překladové klíče, commity), veřejné URL a texty stránek česky, nejnovější standardy HTML/CSS/JS/PHP/Twig, PHP >= 8.2 s declare(strict_types=1), JS jen const/let, složené závorky u každé podmínky, v souborech žádné komentáře, Sass přes @use/@forward.

Cíl
Napojit sekci „Náhradní díly“ na administraci Boltu (/bolt) tak, aby klient spravoval díly i všechny číselníky sám v databázi. V konfiguračních souborech nesmí být žádné konkrétní hodnoty (značky, kategorie, stavy, telefon, ceny dopravy, položky menu). V YAML zůstane jen struktura polí, protože Bolt jinak definovat content typy neumí.

Výchozí stav
- config/bolt/contenttypes.yaml je výchozí z Boltu (homepage, pages, entries, people, blocks, products), typ pro díly chybí.
- public/theme/autoluga/part.twig je statická šablona s natvrdo napsanými daty a placeholdery ([KÓD VÝROBCE], [POČET], [CENA], [DNY], [ČAS], [OD–DO]), blok „Mohlo by se hodit“ (#related) je prázdný.
- taxonomy.yaml a menu.yaml jsou výchozí z Boltu.
- src/Controller, src/Entity a src/Repository jsou prázdné.

Požadavky

1) Content typy (config/bolt/contenttypes.yaml)
Odstraň demo typy, které web nepoužívá (entries, people, products). Zachovej a uprav homepage, pages a blocks.
Číselníky (viewless: true, show_on_dashboard: true, searchable: false, order: sort_order; pole title, slug, sort_order):
- brands (+ logo)
- part_categories (+ icon, relace parent na sebe pro hierarchii)
- part_conditions (+ badge_variant)
- manufacturers
- vehicles (title, model, engine, year_from, year_to, relace brand → brands)
Hlavní typ parts (slug dily, singular part, searchable: true, order: -modifiedAt, default_status: published, records_per_page: 24):
- pole: title, slug (uses title), vehicle_label, price (number float), original_price, stock (number integer), part_code, oe_number, package_contents, images (imagelist, první je hlavní), teaser (textarea), description (redactor), is_featured (checkbox)
- relace: brand → brands, category → part_categories, condition → part_conditions, manufacturer → manufacturers (vše multiple: false), compatible_vehicles → vehicles (multiple: true)
- žádné pole select s values: a žádné taxonomie s options:
Singleton settings: phone, phone_display, address, opening_hours, shipping_cod_price, shipping_days, reservation_cta_label, reservation_note.
Typ menu_items: title, link (interní cesta nebo URL), relace parent, sort_order, is_visible.
Taxonomie: smaž výchozí categories a groups, ponech jen volné tags.
Opakované texty (doprava, montáž) jako záznamy v blocks.

2) Rezervace
Rezervace probíhají jen telefonicky. Žádný formulář, controller, e-mail ani content type reservations. V part.twig odstraň blok #booking, notice-success a navázaný JS (data-form="booking"). Tlačítko „Rezervovat díl“ změň na odkaz tel: s číslem ze settings.phone, text z settings.reservation_cta_label, pod ním settings.reservation_note. V detailu zobraz part_code, aby ho zákazník mohl nadiktovat.

3) Šablony (public/theme/autoluga)
- part.twig: vše čti z record a settings. Breadcrumbs podle kategorie (včetně nadřazené), cena, sleva v % spočtená v Twigu, galerie z record.images, parametry v dl.specs, sklad ze stock, kompatibilita jako smyčka přes compatible_vehicles, sekce „Mohlo by se hodit“ = 4 díly ze stejné kategorie bez aktuálního. Texty dopravy a montáže z blocks a settings, žádné placeholdery.
- partials/_part_card.twig: společná karta dílu pro homepage, výpis i související díly.
- index.twig: sekce #parts vykresluje díly (is_featured nebo posledních 12) přes _part_card a obsahuje malý GET formulář vyhledávání/filtru směřující na /dily.
- listing.twig: výpis s filtrem (q, brand, category, condition, vehicle, price_min, price_max), stránkování, prázdný stav. Možnosti filtru se načítají z DB a nabízí se jen ty, které mají aspoň jeden díl.
- menu: vykresli v Twigu z menu_items (stromově podle parent, řazení sort_order). menu.yaml vyčisti.
- SCSS: dodrž stávající BEM-like pojmenování a design variantu D (světlá) i D1 „Noc“.

4) Backend (src/)
- Repository/PartRepository.php: Doctrine QueryBuilder s join na bolt_relation a bolt_content/bolt_field pro filtrování podle relací, fulltext přes pole title, part_code, oe_number, teaser, stránkování. Použij typované vlastnosti, readonly, enumy, atributy, constructor promotion.
- Controller/PartController.php: route /dily (výpis s filtrem) s validací vstupních parametrů (readonly DTO, Symfony Validator). Detail dílu na /dil/{slug} nech na Boltu (record_template: part.twig).
- config/routes: ověř, že neskoliduje s Boltem. Nastav record_template a listing_template pro parts v config/bolt/config.yaml.

5) Data a migrace
- Vytvoř migraci (doctrine:migrations), pokud ji schéma vyžaduje, a spusť ji.
- Příkaz bin/console app:seed jednorázově naplní počáteční data (značky Renault a Dacia, základní kategorie, stavy, výrobci, několik ukázkových dílů převzatých ze statické šablony, settings, menu_items). Seed je jen úvodní naplnění, dál hodnoty spravuje klient v administraci. Příkaz musí být idempotentní.

6) Ověření
- npm run build, pak bin/console cache:clear (viz CLAUDE.md).
- php -d memory_limit=-1 vendor/bin/ecs check a vendor/bin/phpstan analyse bez chyb.
- Testy v tests/: PartRepository (filtry, kombinace, prázdný výsledek) a PartController (validace parametrů).
- Ruční kontrola v /bolt: založ díl, nahraj fotky, přidej značku a kategorii, ověř detail, výpis, filtr, homepage a menu na desktopu i mobilu a v obou barevných variantách.

Postup
Pracuj po krocích 1 → 5 a po každém kroku krátce shrň, co jsi změnil. Před zásahem do existujících souborů (contenttypes.yaml, part.twig, index.twig, menu.yaml, config.yaml) vytvoř commit nebo kopii, ať jde vrátit zpět. Nic z původních variant D a D1 nemaž. Pokud něco v Boltu 6 nejde udělat tak, jak popisuji (např. filtrování podle relací), napiš alternativu a zeptej se, než ji implementuješ.
