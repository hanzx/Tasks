# Critique: opponent-1

- provider: codex
- model: gpt-5.6-luna
- focus: -
- verdict: reject

## Strengths

- Správně ověřuje aktuální status, cenu a podmínky přístupu místo automatického doporučení.
- Dobře pokrývá zředění, likvidační preference, výpočetní náklady, cash burn a riziko komoditizace modelů.
- Rozumně omezuje velikost pozice a započítává nepřímou AI expozici v portfoliu.
- Repozitář byl ověřen a skutečně obsahuje pouze README.md bez relevantních dat nebo modelu.

## Objections

### O5 [major]

Pravidlo „pokud některý údaj chybí, nelze rozhodnout“ je příliš absolutní a činí rámec prakticky nepoužitelným. U neveřejné firmy budou přesné marže, závazky nebo pravděpodobnost selhání často nedostupné; absence údajů sama o sobě neznamená, že nelze provést konzervativní rozhodnutí.

Suggestion: Rozlišit kritické a nekritické neznámé. Používat intervaly, scénáře a confidence level; při neznámé kritické veličině stanovit konzervativní horní nákupní cenu nebo explicitní „nekupovat za žádnou ověřenou cenu“.

### O6 [major]

Rámec požaduje IRR, scénáře a citlivostní analýzu, ale neurčuje konkrétní výpočetní šablonu ani rozhodovací hranice. Není jasné, jak z tržeb, marží, burn rate, zředění a preferencí získat hodnotu akcie nebo jaké pravděpodobnosti scénářům přidělit.

Suggestion: Doplnit minimální worksheet: vstupní cena a plně zředěný počet akcií, scénářové tržby/marže/burn, potřeba financování, exit hodnota, preference, pravděpodobnosti, kurz, poplatky a daně. Výstupem má být interval IRR a maximální akceptovatelná cena při předem stanoveném prahu.

### O7 [minor]

Tvrzení, že AMZN/GOOGL představují „levnou“ proxy expozici, není podloženo oceněním a může být zavádějící; jejich cena zahrnuje mnoho jiných podniků a samotná citlivost na Anthropic nemusí být významná.

Suggestion: Nahradit „levná“ neutrálním „likvidní, ale nepřesná“ a vyžadovat odhad podílu hodnoty či výsledků Anthropic na celkové hodnotě proxy před jejím použitím.

