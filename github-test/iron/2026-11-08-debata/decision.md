# Decision: Jak rozhodnout, zda nakoupit akcie Anthropicu (rozhodovací rámec, ne doporučení ano/ne)

## Context
Otázka zní, zda je vhodné nakoupit akcie Anthropicu. Repozitář obsahuje jen `README.md` s textem „Test“, takže neexistuje žádný kód, data ani model. „Konkrétní změny“ jsou proto rozhodovací postup, ne změny souborů.

K 8. 11. 2026 nemá autor návrhu ověřená aktuální data: status IPO, cenu, valuaci ani finanční výsledky. Všechna tvrzení o nich platí jako podmínky k ověření, ne jako fakta.

Otázce chybí tři věci:
- profil tazatele (horizont, portfolio, daňová rezidence, tolerance ztráty, zkušenosti),
- způsob přístupu (burza po IPO, soukromé cesty přes sekundár, SPV a fondy, nebo nepřímá expozice přes AMZN, GOOGL a ETF),
- definice „vhodné“. Rozhoduje cena, riziko, likvidita a místo v portfoliu, ne kvalita firmy.

Debata proběhla ve třech kolech mezi tvůrcem (creator) a oponentem `opponent-1`. Oponent v každém kole vydal verdikt „reject“. Lidské rozhodnutí (Decision 1) přijalo návrh ve verzi 1. Zápis tak musí věrně uvést, že verze 1 byla přijata, a zároveň popsat, co se v debatě změnilo a co zůstalo otevřené.

## Options considered
1. **Přímý nákup přes SPV nebo sekundár hned.** Rizika: vrstvy poplatků, právní riziko neplatného převodu, nulová likvidita, informační nevýhoda.
2. **Nepřímá expozice přes AMZN/GOOGL.** V1 ji uvádí jako přijatelný kompromis. Anthropic je jen malá část jejich hodnoty, takže expozice je zředěná.
3. **Počkat na IPO.** V1 ji uvádí jako preferovanou variantu: transparentnost, audit, likvidita, ale s lock-upem a volatilitou.
4. **ETF na AI nebo technologie.** Diverzifikace přes více vítězů, ale bez přesné expozice.
5. **Neinvestovat.** Legitimní výsledek, pokud nejsou splněna kritéria.
6. **„Ano, určitě kup“.** Opírá se o narativ, ne o cenu.

## Decision
**Přijata je verze 1 návrhu (Decision 1).** Jde o podmíněné doporučení: neinvestovat přímo, dokud nejsou splněna čtyři kritéria. Při jejich splnění jen malá satelitní pozice.

Postup podle verze 1:
1. Ověřit stav: proběhlo IPO? Pokud ano, jaká je cena, lock-up a float. Pokud ne, jaké je poslední kolo a sekundární cena.
2. Zpracovat scénářový model ve třech variantách (základní, optimistická, pesimistická) s pravděpodobnostmi.
3. Spočítat čisté náklady přístupu (poplatky, daň, kurz CZK/USD).
4. Zkontrolovat správu a strukturu: třídy akcií, preferenční práva a Long-Term Benefit Trust.
5. Rozhodnout podle pravidla: „ano“ jen při očekávaném výnosu ≥ 20 % po poplatcích a splněných K1–K4.

Kritéria z verze 1:
- **K1 Přístup bez vysokých poplatků.** Celkové náklady SPV (carry 10–20 %, správa, vrstvy poplatků) nesmí výrazně zhoršit očekávaný výnos. Převod musí být legitimní (ROFR, souhlas firmy).
- **K2 Cena.** Scénářový odhad: tržby za 3–5 let × výstupní násobek × (1 − zřeďování) vůči dnešní ceně. Požadovaný očekávaný výnos je alespoň 20–25 % ročně.
- **K3 Velikost.** Maximálně 1–5 % likvidního jmění, s možností úplné ztráty a zamčením kapitálu na 5–10 let.
- **K4 Neduplicita.** Kdo drží globální ETF nebo Nasdaq, má už nepřímou expozici. Přímá pozice koncentruje riziko do AI.

**Důležité upozornění k tomuto rozhodnutí:** verze 1 neobsahuje změny z pozdějších kol. Debata po ní zpřesnila návrh ve verzích 2 a 3, ale lidské rozhodnutí přijalo verzi 1. Zlepšení z kol 1 a 2 proto nejsou součástí přijatého textu. Níže jsou uvedena jako doporučené úpravy, které tvůrce přijal a které by měly být zapracovány. Ostatní tvrzení v tomto zápisu se opírají jen o verzi 1.

Úpravy přijaté tvůrcem v debatě, které přijatá verze 1 neobsahuje:
- **Brána ověření (O1).** Bez ověřeného statusu a ceny je výsledek „nelze rozhodnout“, ne „neinvestovat“.
- **Odvozený práh výnosu (O2).** Požadovaný výnos je bezriziková sazba plus akciová prémie plus prémie za nelikviditu a koncentraci, upravený o pravděpodobnost úplné ztráty. Čísla 20–25 % zůstávají jen ilustrací.
- **AI ekonomika (O3).** Do modelu patří marže po inferenci, výpočetní závazky, cash burn, financování, likvidační preference, třídy akcií a fully diluted báze.
- **Strop pozice (O4).** Výchozí strop je pod 1 % likvidního jmění pro neznámého nebo nezkušeného investora. Navýšení je podmíněno rizikovým rozpočtem, celkovou expozicí na AI a schopností snést úplnou ztrátu.
- **Kritické a nekritické neznámé (O5).** Kritická neznámá s nízkou jistotou vede ke konzervativní horní nákupní ceně, nebo k výsledku „nekupovat za žádnou neověřenou cenu“.
- **Worksheet (O6).** Vstupy, postup od tržeb po hodnotu akcie, výstup (interval IRR a maximální cena) a výchozí pravidlo, že pesimistický scénář nemá váhu pod 25 %.
- **Proxy (O7).** AMZN/GOOGL jsou „likvidní, ale nepřesná“ proxy. Před použitím je nutné odhadnout podíl Anthropic na jejich hodnotě.

## Rejected alternatives
- **Přímý nákup přes SPV hned.** Nikdo se za něj v debatě nezasazoval. Verze 1 ho zamítla pro vrstvy poplatků, právní riziko převodu, nulovou likviditu a informační nevýhodu. Zůstává možný jen při splnění K1–K4.
- **„Ano, určitě kup“.** Nikdo se za něj v debatě nezasazoval. Zamítnuto, protože se opírá o narativ, ne o cenu.
- **Neutrální závěr „nelze rozhodnout“ jako jediný výstup.** Prosazoval `opponent-1` (O1). Tvůrce ho přijal ve verzi 2 jako bránu ověření. Lidské rozhodnutí přijalo verzi 1, takže tato brána nebyla přijata.
- **Strop pod 1 % místo 1–5 %.** Prosazoval `opponent-1` (O4). Tvůrce ho přijal ve verzi 2. Verze 1 s rozpětím 1–5 % byla přijata, takže zpřesnění zatím neplatí. Zůstává jako otevřené riziko.
- **Odvozený práh výnosu místo pevných 20–25 %.** Prosazoval `opponent-1` (O2). Tvůrce ho přijal ve verzi 2. V přijaté verzi 1 zůstává pevný práh.
- **Rozšíření modelu o AI ekonomiku, worksheet a rozlišení neznámých.** Prosazoval `opponent-1` (O3, O5, O6). Tvůrce to přijal ve verzích 2 a 3. Verze 1 to neobsahuje.
- **Ocenění proxy AMZN/GOOGL bez slova „levná“ a s odhadem podílu.** Prosazoval `opponent-1` (O7). Tvůrce to přijal ve verzi 3. Verze 1 popisuje proxy jako „likvidní a levnou“.

## Open risks
Oponent v žádném kole verdikt „reject“ neodvolal. Níže jsou dvě námitky, které zůstaly otevřené, a následně všechny námitky, které jsou sice resolved, ale nejsou zapracovány v přijaté verzi 1.

**Otevřené námitky (status=open):**
- **O8 [major] – zjednodušené zředění.** Worksheet počítá budoucí zředění jako „nové akcie ÷ stávající“. Zředění ale závisí na částce financování, ceně kol, opčních poolech, konvertibilech a warrantech. Maximální akceptovatelná cena tak může vyjít výrazně nadhodnocená. Oponent navrhuje modelovat jednotlivá budoucí kola a cap table v každém scénáři. Tvůrce na tuto námitku neodpověděl.
- **O9 [major] – průměrování IRR.** Verze 3 uvádí vážený průměr scénářových IRR. IRR je nelineární a toky mají různé načasování, takže průměr může vytvořit falešný dojem, že investice překonává požadovaný výnos. Oponent navrhuje očekávanou NPV při požadovaném výnosu, maximální cenu jako cenu s NPV rovnou nule a IRR jen doplňkově. Má se ukazovat i pravděpodobnost ztráty. Tvůrce na tuto námitku neodpověděl. Obě námitky se týkají worksheetu z verze 3. Přijatá verze 1 worksheet neobsahuje, ale kdyby ho někdo zavedl, musí je vyřešit.

**Námitky označené resolved, ale nezapracované do přijaté verze 1:**
- **O1 [blocker]:** verze 1 stále doporučuje „neinvestovat za současných podmínek“ bez ověření podmínek. Závěr je tak určitější, než dovolují podklady.
- **O2 [major]:** pevný práh 20–25 % ročně nemá odvození z horizontu, pravděpodobnosti ztráty, alternativního výnosu ani likviditní prémie. Hrozí falešná přesnost.
- **O3 [major]:** model „tržby × násobek“ ignoruje marži po inferenci, cash burn, výpočetní závazky, preference a financování.
- **O4 [major]:** rozpětí 1–5 % likvidního jmění je příliš široké pro nezkušeného investora.
- **O5 [major]:** zpřesnění zacházení s chybějícími údaji (kritické × nekritické neznámé) ve verzi 1 chybí.
- **O6 [major]:** ve verzi 1 chybí výpočetní šablona a rozhodovací hranice.
- **O7 [minor]:** verze 1 označuje AMZN/GOOGL jako „levnou“ proxy, což je nepodložené a může být zavádějící. Tato minor námitka byla v pozdějších verzích řešena, ale v přijaté verzi 1 ne.

**Další rizika uvedená ve verzi 1:**
- Valuační riziko: cena předpokládá pokračování exponenciálního růstu.
- Konkurence a komoditizace modelů (OpenAI, Google, Meta, otevřené a čínské modely).
- Kapitálová náročnost, závislost na dodavatelích (Nvidia, cloud) a zřeďování.
- Regulace a spory (autorská práva, bezpečnostní regulace).
- Struktura vlastnictví: Long-Term Benefit Trust a charakter public benefit společnosti mohou omezit prosazování zájmů akcionářů.
- Riziko AI bubliny a korelace se sektorem.
- Likvidita, kurz CZK/USD a daně. V ČR platí test tří let u cenných papírů, u neveřejných podílů a zahraničních vehikul se režim může lišit, nutná je konzultace.

**Otázky, které zůstaly nevyřešeny:**
- Je Anthropic veřejně obchodovaný a za jakou cenu?
- Je pevný práh 20–25 % obhajitelný?
- Je strop 1–5 % správný?

**Upozornění:** Jde o analytický rámec, ne o individuální investiční poradenství.
