# Proposal v2

- author: creator
- provider: claude-code
- model: claude-sonnet-5-5
- round: 2

# Návrh v2: Je vhodné nakoupit akcie Anthropicu?

## 0. Poznámka k podkladům
Repozitář obsahuje jen `README.md` s textem „Test“. Žádný kód, data ani model k analýze neexistují. „Konkrétní změny“ proto nejsou změny v souborech, ale rozhodovací postup. Nemám ověřená aktuální data k 8. 11. 2026 (status IPO, cena, valuace, finanční výsledky). Všechna tvrzení o nich jsou podmínky k ověření, ne fakta.

**Závěr při současných podkladech: nelze rozhodnout.** Návrh dává rozhodovací rámec a pravidla, ne ano/ne.

## 1. Problém
Otázka postrádá:
1. **Profil tazatele:** horizont, velikost a složení portfolia, daňovou rezidenci (pravděpodobně ČR), toleranci ztráty, zkušenosti.
2. **Způsob přístupu:** veřejná burza (po IPO), nebo soukromé cesty (sekundár, SPV, fondy), nebo nepřímá expozice (AMZN, GOOGL, ETF).
3. **Definici „vhodné“:** nejde o kvalitu firmy, ale o cenu, riziko, likviditu a místo v portfoliu.

## 2. Krok 0 – brána ověření (povinná před jakýmkoli závěrem)
Doložit z primárních zdrojů (prospekt/S-1, oznámení firmy, platforma, broker):
- status: veřejně obchodovaný? Jinak poslední primární kolo a sekundární cena,
- cena, valuace (post-money i fully diluted), poslední tržby a jejich run-rate,
- hrubá marže po nákladech na inferenci, cash burn, výpočetní závazky, plánované financování,
- třída akcií, kterou lze koupit (common × preferred), a její práva,
- podmínky převodu (ROFR, souhlas firmy, lock-up), úplné náklady přístupu,
- profil investora (viz sekce 1).

Pokud některý údaj chybí, výsledek je „nelze rozhodnout“, nikoli „ne“.

## 3. Rozhodovací pravidlo po ověření
### 3.1 Větev A – Anthropic je veřejný
Odpadá problém přístupu. Rozhoduje cena vůči scénářům (3.3), lock-up/volatilita po IPO a limit pozice (3.4). Při nejasné ceně je přijatelný postupný nákup (rozložení do času).

### 3.2 Větev B – Anthropic je soukromý
Přímý nákup jen pokud jsou splněny všechny podmínky:
- **Legitimní převod:** doložené schválení firmy, žádná neplatná SPV vrstva, nízké celkové poplatky (carry, správa, vrstvy).
- **Kladný očekávaný výnos nad prahem** (3.3).
- **Limit pozice** (3.4).
- **Neduplicita:** kdo drží globální ETF/Nasdaq, AMZN, GOOGL, má už nepřímou expozici; ta se započítá do limitu AI.
Jinak preferovat počkat na IPO nebo omezit se na likvidní proxy (AMZN/GOOGL – zředěná, ale levná a likvidní expozice).

### 3.3 Odvození požadovaného výnosu a ocenění
**Práh není pevné číslo.** Odvodí se:
požadovaný výnos ≈ bezriziková sazba + akciová prémie + prémie za nelikviditu a koncentraci, přičemž očekávaný výnos se počítá z rozdělení výsledků včetně **pravděpodobnosti úplné či téměř úplné ztráty**.
- Výstup: **IRR po poplatcích, dani a zředění v CZK** (vč. kurzu), ne hrubý výnos.
- Alternativní náklad: výnos globálního ETF při nižším riziku a plné likviditě. Pozice musí tuto alternativu překonat o prémii za riziko.
- Čísla jako 20–25 % ročně jsou jen **ilustrace** typické prémie u neobchodovatelného aktiva, nikoli závazné pravidlo.
- Povinná **citlivostní analýza**: horizont (3–10 let), výstupní násobek, marže, zředění, pravděpodobnost ztráty.

**Ocenění – ekonomika AI, ne jen tržby × násobek:**
- jednotková ekonomika: hrubá marže po inferenci, trend nákladů na jednotku výpočtu, koncentrace zákazníků,
- cash flow: burn, kapitálové výdaje a dlouhodobé výpočetní závazky (cloud, čipy),
- financování: očekávaná další kola a zřeďování; valuace vždy fully diluted,
- kapitálová struktura: likvidační preference, třídy akcií, pořadí nároků. Cena sekundáru za common není srovnatelná s cenou preferred v posledním kole a v nepříznivém scénáři mohou preference výrazně ponížit hodnotu common,
- tři scénáře (základní, optimistický, pesimistický) s pravděpodobnostmi, včetně scénáře „komoditizace modelů“.

### 3.4 Velikost pozice
- **Výchozí strop pro neznámého či nezkušeného investora: pod 1 % likvidního jmění**, jako „malá satelitní pozice“ s předpokladem možné úplné ztráty a zamčení kapitálu na 5–10 let.
- Navýšení nad tuto hranici jen když investor doloží: (a) explicitní rizikový rozpočet, (b) **celkovou expozici na AI** (ETF, AMZN/GOOGL, zaměstnanecké akcie, jiné soukromé pozice), (c) schopnost snést úplnou ztrátu bez zásahu do likvidní rezervy (min. několik měsíců výdajů mimo investice) a cílů.
- Celková expozice na AI se omezuje jako celek, ne po jednotlivých titulech.

## 4. Alternativy
| Alternativa | Hodnocení |
|---|---|
| Přímý nákup přes SPV hned | Vrstvy poplatků, právní riziko převodu, nulová likvidita, informační nevýhoda. Jen při splnění 3.2. |
| AMZN/GOOGL jako proxy | Zředěná, ale likvidní a levná; přijatelný kompromis. |
| Počkat na IPO | Obvykle preferovaná varianta při neveřejném statusu: transparentnost, audit, likvidita; počítat s lock-upem a volatilitou. |
| ETF na AI/technologie | Diverzifikace, ale ne přesná expozice. |
| Neinvestovat | Legitimní výsledek, pokud po bráně ověření nevychází kladný očekávaný výnos nad prahem. |
| „Ano, určitě kup“ | Zamítnuto: opírá se o narativ, ne o cenu. |

## 5. Rizika
- valuace předpokládá pokračování rychlého růstu,
- konkurence a komoditizace modelů (OpenAI, Google, Meta, otevřené a čínské modely),
- kapitálová náročnost, závislost na dodavatelích čipů a cloudu, zřeďování,
- regulace a spory (autorská práva, bezpečnost),
- struktura správy (Long-Term Benefit Trust, charakter public benefit společnosti) může omezit prosazování zájmů akcionářů,
- riziko AI bubliny a korelace se sektorem,
- likvidita, kurz CZK/USD, daně (v ČR test tří let u cenných papírů, u neveřejných podílů a zahraničních vehikul se režim může lišit – konzultace daňového poradce).

## 6. Otevřené otázky
1. Jaký je ověřený status a cena (výsledek kroku 0)?
2. Je odvození požadovaného výnosu (3.3) dostatečně operacionalizované, nebo potřebuje konkrétní výchozí parametry?
3. Je limit pod 1 % vhodný jako výchozí, nebo příliš konzervativní pro zkušeného investora?
4. Jak započítat nepřímou expozici (AMZN/GOOGL, ETF) do limitu AI?

**Upozornění:** Jde o analytický rámec, ne o individuální investiční poradenství.
