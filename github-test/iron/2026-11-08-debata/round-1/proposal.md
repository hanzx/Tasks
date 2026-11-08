# Proposal v1

- author: creator
- provider: claude-code
- model: claude-sonnet-5-5
- round: 1

# Návrh v1: Je vhodné nakoupit akcie Anthropicu?

## 0. Poznámka k podkladům
Repozitář obsahuje jen `README.md` s textem „Test“. Žádný kód, data ani model k analýze neexistují. „Konkrétní změny“ proto nejsou změny v souborech, ale investiční rozhodnutí a jeho postup. Nemám ověřená aktuální data (cena, valuace, stav IPO k 8. 11. 2026). Tvrzení o nich proto uvádím jako podmínky, které je potřeba ověřit, ne jako fakta.

## 1. Problém, jak mu rozumím
Otázka zní, zda je „vhodné“ koupit akcie Anthropicu. Chybí v ní tři věci, bez nichž nelze odpovědět ano/ne:
1. **Kdo se ptá a s jakým cílem.** Chybí horizont, velikost pozice, daňová rezidence (pravděpodobně ČR, podle e-mailu .cz) a tolerance ztráty.
2. **Kde se akcie dají koupit.** Anthropic je podle mých informací soukromá firma. Pokud neproběhlo IPO, běžné akcie na burze neexistují. Dostupné jsou jen:
   - sekundární trhy a SPV (Forge, EquityZen a podobné),
   - fondy a vehikly s expozicí k firmě,
   - nepřímá expozice přes Amazon (AMZN) a Alphabet (GOOGL), kteří jsou investory.
3. **„Vhodné“ není stejné co „výnosné“.** Rozhodují cena, riziko, likvidita a místo v portfoliu, ne kvalita firmy.

## 2. Zvolený přístup (teze)
**Doporučení: Neinvestovat přímo za současných podmínek, pokud nejsou splněna čtyři kritéria. Pokud ano, jen malou satelitní pozici.**

Dobrá firma a dobrá investice jsou dvě různé věci. Anthropic má silné produkty, rychlý růst tržeb a vedoucí postavení u firemních zákazníků. To je ale z velké části už zahrnuto v ceně posledních kol.

Kritéria pro „ano“:
- **K1 Přístup bez vysokých poplatků.** Celkové náklady SPV (carry 10–20 %, správa, vrstvy poplatků) nesmí výrazně zhoršit očekávaný výnos. Zároveň musí jít o legitimní převod, protože firma obvykle omezuje převody akcií (ROFR, souhlas) a SPV bývají právně sporné.
- **K2 Cena.** Valuace vůči run-rate tržbám musí být obhajitelná. Výchozí nástroj je scénářový odhad: tržby za 3–5 let × výstupní násobek × (1 − zřeďování) vůči dnešní ceně. Požadovaný očekávaný výnos je alespoň 20–25 % ročně, protože jde o neobchodovatelné aktivum.
- **K3 Velikost.** Maximálně 1–5 % likvidního jmění, s tím, že lze počítat s úplnou ztrátou a se zamčením kapitálu na 5–10 let.
- **K4 Neduplicita.** Kdo dr��í globální ETF nebo Nasdaq, má už nepřímou expozici (Amazon, Alphabet, Microsoft/Nvidia přes ekosystém). Přímá pozice koncentruje riziko do AI.

## 3. Konkrétní postup (místo změn v kódu)
1. Ověřit stav: proběhlo IPO? Pokud ano, jaká je cena, lock-up a float. Pokud ne, jaké je poslední kolo a sekundární cena.
2. Provést scénářový model ve třech variantách (základní, optimistická, pesimistická) s pravděpodobnostmi.
3. Spočítat čisté náklady přístupu (poplatky, daň, kurz CZK/USD).
4. Zkontrolovat správu a strukturu: třídy akcií, preferenční práva investorů, struktura Long-Term Benefit Trust a kontrola investorů.
5. Rozhodnout podle pravidla: výsledek je „ano“ jen při očekávaném výnosu ≥ 20 % po poplatcích a splněných K1–K4.

## 4. Zvažované alternativy a proč ne
| Alternativa | Proč zamítnuta / omezena |
|---|---|
| Koupit přes SPV hned | Vrstvy poplatků, právní riziko neplatného převodu, nulová likvidita, informační nevýhoda oproti insiderům. |
| Koupit AMZN/GOOGL jako proxy | Anthropic je malá část jejich hodnoty, takže expozice je zředěná. Je to ale likvidní a levné. **Přijatelný kompromis** pro tvrdou touhu po expozici. |
| Počkat na IPO | Preferovaná varianta. IPO často přichází při vysoké ceně, ale poskytuje transparentnost, audit a likviditu. Je nutné počítat s lock-upem a s volatilitou po IPO. |
| Sázka na celý AI sektor (ETF) | Diverzifikace přes více vítězů. Slabší je tím, že nezachytí případný převis jednoho vítěze. |
| „Ano, určitě kup“ | Zamítnuto. Opírá se o narativ, ne o cenu. |

## 5. Rizika
- **Valuační riziko:** cena předpokládá pokračování exponenciálního růstu. Jakékoli zpomalení znamená výrazný pokles.
- **Konkurence a komoditizace modelů:** OpenAI, Google, Meta, otevřené modely a čínští konkurenti snižují cenovou sílu.
- **Kapitálová náročnost:** výpočetní kapacita stojí desítky miliard. Hrozí zřeďování a závislost na dodavatelích (Nvidia, cloud).
- **Regulace a právní spory** (autorská práva, bezpečnostní regulace).
- **Struktura vlastnictví:** Long-Term Benefit Trust a mise veřejně prospěšné společnosti mohou omezit prosazování zájmu akcionářů.
- **Riziko bubliny v AI:** korelace s celým sektorem v případě korekce.
- **Likvidita, daně a právní riziko:** viz výše. V ČR platí test tří let u cenných papírů, ale u neveřejných podílů a zahraničních vehikul se režim liší, nutná konzultace.

## 6. Otevřené otázky (pro oponenty)
1. Je Anthropic k dnešku veřejně obchodovaný? Pokud ano, celá analýza přístupu (K1) odpadá a zůstává jen cena.
2. Jaký očekávaný výnos je realistický, a je prahová hodnota 20–25 % obhajitelná?
3. Je 1–5 % správný strop, nebo je pro nezkušeného investora příliš vysoký?
4. Je proxy přes AMZN/GOOGL lepší, než se čeká?
5. Je vůbec správné dávat obecné doporučení bez znalosti situace tazatele?

**Upozornění:** Jde o analytický rámec, ne o individuální investiční poradenství.
