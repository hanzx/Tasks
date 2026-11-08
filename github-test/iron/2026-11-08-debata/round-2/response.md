# Creator response

- author: creator
- provider: claude-code
- model: claude-sonnet-5-5
- round: 2

## Responses

- opponent-1/O5: accepted - Absolutní pravidlo „chybí údaj ⇒ nelze rozhodnout“ bylo nepraktické. V sekci 2 nově rozlišuji kritické a nekritické neznámé. Nekritické se nahradí intervaly a konzervativními předpoklady. U kritických neznámých se použije buď konzervativní horní nákupní cena, nebo výsledek „nekupovat za žádnou neověřenou cenu“. Každý odhad nese úroveň jistoty (vysoká, střední, nízká). Status a cenu to netýká: bez nich rozhodnutí o nákupu nelze udělat.
- opponent-1/O6: accepted - Přidal jsem minimální worksheet (sekce 3.5) se vstupy, postupem od tržeb po hodnotu common akcie, výstupem (interval IRR a maximální akceptovatelná cena) a rozhodovacími hranicemi. Pravděpodobnosti scénářů nestanovuji jako fakt. Dávám výchozí pravidlo: pesimistický scénář nesmí mít váhu pod 25 % a všechny váhy musí být odůvodněné a podrobené citlivostní analýze. Zvolené hodnoty jsou ilustrativní výchozí body, ne předpověď.
- opponent-1/O7: accepted - Slovo „levná“ jsem odstranil. AMZN/GOOGL jsou popsány jako „likvidní, ale nepřesná“ proxy. Před jejich použitím je nově nutné odhadnout podíl hodnoty či výsledků Anthropic na hodnotě proxy (sekce 3.2 a tabulka alternativ). Je-li podíl nevýznamný, proxy se nepovažuje za expozici na Anthropic.

## Proposal

# Návrh v3: Je vhodné nakoupit akcie Anthropicu?

## 0. Poznámka k podkladům
Repozitář obsahuje jen `README.md` s textem „Test“. Žádný kód, data ani model k analýze neexistují. „Konkrétní změny“ proto nejsou změny v souborech, ale rozhodovací postup. Nemám ověřená aktuální data k 8. 11. 2026 (status IPO, cena, valuace, finanční výsledky). Všechna tvrzení o nich jsou podmínky k ověření, ne fakta.

**Závěr při současných podkladech: nelze rozhodnout.** Důvodem je chybějící status a cena (kritické údaje, viz sekce 2), ne obecná neurčitost. Návrh dává rozhodovací rámec a pravidla, ne ano/ne.

## 1. Problém
Otázka postrádá:
1. **Profil tazatele:** horizont, velikost a složení portfolia, daňovou rezidenci (pravděpodobně ČR), toleranci ztráty, zkušenosti.
2. **Způsob přístupu:** veřejná burza (po IPO), nebo soukromé cesty (sekundár, SPV, fondy), nebo nepřímá expozice (AMZN, GOOGL, ETF).
3. **Definici „vhodné“:** nejde o kvalitu firmy, ale o cenu, riziko, likviditu a místo v portfoliu.

## 2. Krok 0 – brána ověření a zacházení s neznámými
### 2.1 Tvrdé údaje (bez nich žádné rozhodnutí o nákupu)
Doložit z primárních zdrojů (prospekt/S-1, oznámení firmy, platforma, broker):
- status: veřejně obchodovaný? Jinak poslední primární kolo a sekundární cena,
- aktuální nabídnutá cena a třída akcií (common × preferred) s právy,
- podmínky převodu (ROFR, souhlas firmy, lock-up) a úplné náklady přístupu,
- profil investora (sekce 1).

Chybí-li některý z nich, výsledek je „nelze rozhodnout“.

### 2.2 Odhadovatelné údaje (chybějící hodnota nebrání rozhodnutí)
Tržby a run-rate, hrubá marže po inferenci, cash burn, výpočetní závazky, plánované financování, fully diluted počet akcií, likvidační preference.
- Každý údaj se zadá jako **interval** (nízký / střední / vysoký) s **úrovní jistoty** (vysoká = z primárního zdroje, střední = z důvěryhodných médií či analýz, nízká = vlastní odhad).
- **Kritické neznámé** = ty, jejichž rozumný rozsah mění závěr (typicky fully diluted počet akcií, preference, marže, výpočetní závazky). Pokud je kritická neznámá s nízkou jistotou, rozhodnutí se řídí konzervativním krajním koncem intervalu a výsledkem je jedno z:
  - **konzervativní horní nákupní cena** spočtená z pesimistického konce intervalu (3.5), nebo
  - **„nekupovat za žádnou neověřenou cenu“**, pokud ani při konzervativních předpokladech žádná rozumná cena práh nesplní.
- **Nekritické neznámé** se doplní střední hodnotou a otestují v citlivostní analýze.

## 3. Rozhodovací pravidlo po ověření
### 3.1 Větev A – Anthropic je veřejný
Odpadá problém přístupu. Rozhoduje cena vůči maximální akceptovatelné ceně z worksheetu (3.5), lock-up/volatilita po IPO a limit pozice (3.4). Při nejasné ceně je přijatelný postupný nákup (rozložení do času).

### 3.2 Větev B – Anthropic je soukromý
Přímý nákup jen pokud jsou splněny všechny podmínky:
- **Legitimní převod:** doložené schválení firmy, žádná neplatná SPV vrstva, nízké celkové poplatky (carry, správa, vrstvy).
- **Cena pod maximální akceptovatelnou cenou** (3.5).
- **Limit pozice** (3.4).
- **Neduplicita:** kdo drží globální ETF/Nasdaq, AMZN, GOOGL, má už nepřímou expozici; ta se započítá do limitu AI.

Jinak preferovat počkat na IPO. Proxy (AMZN/GOOGL) je **likvidní, ale nepřesná** náhrada: před použitím je nutné odhadnout podíl hodnoty nebo výsledků Anthropic (např. přes držený podíl a jeho ocenění) na celkové hodnotě proxy. Je-li podíl nevýznamný, nepovažuje se za expozici na Anthropic a nezapočítává se jako náhrada, jen jako (malá) položka v limitu AI.

### 3.3 Odvození požadovaného výnosu a ocenění
**Práh není pevné číslo.** Odvodí se:
požadovaný výnos ≈ bezriziková sazba + akciová prémie + prémie za nelikviditu a koncentraci, přičemž očekávaný výnos se počítá z rozdělení výsledků včetně **pravděpodobnosti úplné či téměř úplné ztráty**.
- Výstup: **IRR po poplatcích, dani a zředění v CZK** (vč. kurzu), ne hrubý výnos.
- Alternativní náklad: výnos globálního ETF při nižším riziku a plné likviditě. Pozice musí tuto alternativu překonat o prémii za riziko.
- Čísla jako 20–25 % ročně jsou jen **ilustrace** typické prémie u neobchodovatelného aktiva, nikoli závazné pravidlo.
- Povinná **citlivostní analýza**: horizont (3–10 let), výstupní násobek, marže, zředění, pravděpodobnost ztráty.

**Ocenění – ekonomika AI, ne jen tržby × násobek:** jednotková ekonomika (marže po inferenci, trend nákladů na výpočet, koncentrace zákazníků), cash flow (burn, capex, dlouhodobé výpočetní závazky), financování a zřeďování (valuace vždy fully diluted), kapitálová struktura (likvidační preference, třídy akcií; cena sekundáru za common není srovnatelná s cenou preferred posledního kola).

### 3.4 Velikost pozice
- **Výchozí strop pro neznámého či nezkušeného investora: pod 1 % likvidního jmění**, jako „malá satelitní pozice“ s předpokladem možné úplné ztráty a zamčení kapitálu na 5–10 let.
- Navýšení nad tuto hranici jen když investor doloží: (a) explicitní rizikový rozpočet, (b) **celkovou expozici na AI** (ETF, AMZN/GOOGL, zaměstnanecké akcie, jiné soukromé pozice), (c) schopnost snést úplnou ztrátu bez zásahu do likvidní rezervy (min. několik měsíců výdajů mimo investice) a cílů.
- Celková expozice na AI se omezuje jako celek, ne po jednotlivých titulech.

### 3.5 Minimální worksheet (od vstupů k maximální ceně)
**Vstupy:**
1. nabízená cena za akcii, třída akcií, fully diluted počet akcií (interval),
2. pro každý scénář a rok horizontu: tržby, provozní marže (po inferenci), burn / kapitálové potřeby,
3. potřeba externího financování a z toho zředění (nové akcie ÷ stávající),
4. exit: výstupní násobek (tržby nebo cash flow) a rok výstupu,
5. kapitálová struktura: likvidační preference ve vodopádu,
6. náklady: poplatky vehikula, daň, kurz CZK/USD.

**Postup:**
1. Exit equity value = tržby v roce výstupu × násobek (+ čistá hotovost − dluh).
2. Vodopád: nejprve likvidační preference seniorních tříd, zbytek na common a konvertované akcie. Z toho hodnota jedné akcie dané třídy.
3. Úprava o zředění z budoucích kol.
4. Přepočet do CZK, odečet poplatků a daně, výsledné cash-on-cash a IRR.
5. Vážený průměr scénářů.

**Pravděpodobnosti scénářů (výchozí pravidlo, ne předpověď):** minimálně tři scénáře (pesimistický vč. komoditizace modelů, základní, optimistický). Pesimistický nesmí mít váhu pod 25 % a musí obsahovat ztrátu většiny kapitálu. Váhy musí být písemně zdůvodněny a v citlivostní analýze se posune každá o ±10 p. b. Pokud závěr přežije jen jednu sadu vah, je považován za nespolehlivý.

**Výstup:**
- **interval IRR** (od pesimistické po optimistickou sadu parametrů) po poplatcích, dani, zředění v CZK,
- **maximální akceptovatelná cena** = cena, při které vážený IRR rovná požadovanému výnosu (3.3) a zároveň pesimistický scénář nepřekročí rizikový rozpočet (3.4),
- **rozhodovací hranice:** cena ≤ max. akceptovatelná → nákup možný v rámci limitu; cena nad ní → nekupovat či počkat; kritická neznámá s nízkou jistotou → použít konzervativní cenu podle 2.2.

## 4. Alternativy
| Alternativa | Hodnocení |
|---|---|
| Přímý nákup přes SPV hned | Vrstvy poplatků, právní riziko převodu, nulová likvidita, informační nevýhoda. Jen při splnění 3.2. |
| AMZN/GOOGL jako proxy | Likvidní, ale nepřesná; vyžaduje odhad podílu Anthropic na hodnotě proxy (3.2). Při nevýznamném podílu nejde o expozici na Anthropic. |
| Počkat na IPO | Obvykle preferovaná varianta při neveřejném statusu: transparentnost, audit, likvidita; počítat s lock-upem a volatilitou. |
| ETF na AI/technologie | Diverzifikace, ale ne přesná expozice. |
| Neinvestovat | Legitimní výsledek, pokud cena nesplní práh nebo platí „nekupovat za žádnou neověřenou cenu“. |
| „Ano, určitě kup“ | Zamítnuto: opírá se o narativ, ne o cenu. |

## 5. Rizika
- valuace předpokládá pokračování rychlého růstu,
- konkurence a komoditizace modelů (OpenAI, Google, Meta, otevřené a čínské modely),
- kapitálová náročnost, závislost na dodavatelích čipů a cloudu, zřeďování,
- regulace a spory (autorská práva, bezpečnost),
- struktura správy (Long-Term Benefit Trust, charakter public benefit společnosti) může omezit prosazování zájmů akcionářů,
- riziko AI bubliny a korelace se sektorem,
- riziko modelu: výsledek worksheetu je citlivý na odhady s nízkou jistotou,
- likvidita, kurz CZK/USD, daně (v ČR test tří let u cenných papírů, u neveřejných podílů a zahraničních vehikul se režim může lišit – konzultace daňového poradce).

## 6. Otevřené otázky
1. Jaký je ověřený status a cena (výsledek kroku 2.1)?
2. Jsou výchozí váhy scénářů (pesimistický ≥ 25 %) a posun ±10 p. b. vhodné, nebo je třeba kalibrace?
3. Je limit pod 1 % vhodný jako výchozí, nebo příliš konzervativní pro zkušeného investora?
4. Jakou metodou odhadovat podíl Anthropic na hodnotě AMZN/GOOGL proxy a jak jej započítat do limitu AI?

**Upozornění:** Jde o analytický rámec, ne o individuální investiční poradenství.
