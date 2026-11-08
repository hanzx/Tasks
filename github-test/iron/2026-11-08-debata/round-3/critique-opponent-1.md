# Critique: opponent-1

- provider: codex
- model: gpt-5.6-luna
- focus: -
- verdict: reject

## Strengths

- Návrh správně ověřuje status, cenu a podmínky přístupu místo automatického doporučení.
- Dobře pokrývá AI ekonomiku, cash burn, výpočetní závazky, likvidační preference, zředění a koncentraci rizika.
- Rozumně pracuje s intervaly, úrovní jistoty, scénáři a limitem malé satelitní pozice.
- Ověření repozitáře odpovídá návrhu: obsahuje pouze README.md s textem „Test“ a žádný relevantní model.

## Objections

### O8 [major]

Worksheet zachází s budoucím zředěním příliš zjednodušeně jako s „nové akcie ÷ stávající“. Zředění závisí na částce financování, ceně v jednotlivých kolech, opčních poolech, konvertibilních nástrojích a warrant­ech; bez těchto vazeb může maximální akceptovatelná cena vyjít výrazně nadhodnocená.

Suggestion: Modelovat pro každý scénář jednotlivá budoucí kola a cap table: potřebný kapitál, post-money valuaci, emisní cenu, nové akcie, opce, konvertibly/warranty a následný fully diluted podíl investora. Teprve z této projekce počítat hodnotu akcie a maximální cenu.

### O9 [major]

Postup výslovně uvádí „vážený průměr“ scénářových IRR. Aritmetické průměrování IRR není obecně správné, protože IRR je nelineární a scénáře mohou mít odlišné načasování i velikost peněžních toků; může tak vzniknout falešný dojem, že investice překonává požadovaný výnos.

Suggestion: Pro každou scénářovou sadu počítat očekávané peněžní toky nebo očekávanou čistou současnou hodnotu při požadovaném výnosu. Maximální cenu definovat jako cenu, při níž očekávaná NPV dosáhne nuly, a IRR uvádět pouze doplňkově; současně zobrazit pravděpodobnost ztráty a ztrátu v nepříznivém scénáři.

