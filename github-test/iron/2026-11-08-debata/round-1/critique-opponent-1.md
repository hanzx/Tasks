# Critique: opponent-1

- provider: codex
- model: gpt-5.6-luna
- focus: -
- verdict: reject

## Strengths

- Repozitář skutečně obsahuje pouze README.md s textem „Test“, takže návrh správně netvrdí, že existuje relevantní kód nebo interní investiční model.
- Správně rozlišuje kvalitu firmy od atraktivity ceny a upozorňuje na likviditu, poplatky, zředění, právní strukturu a koncentraci rizika.
- Rozumně odmítá automatické doporučení „určitě kupovat“ a navrhuje ověřit přístup, náklady a scénáře.

## Objections

### O1 [blocker]

Návrh uvádí doporučení „neinvestovat přímo za současných podmínek“, ale současné podmínky vůbec neověřuje. Nevíme, zda je Anthropic veřejně obchodovaný, za jakou cenu lze expozici získat ani jaká je aktuální valuace. U finančního rozhodnutí proto závěr působí určitěji, než dovolují podklady.

Suggestion: Nejprve ověřit aktuální status, cenu, valuaci, podmínky přístupu a poslední finanční údaje. Do té doby formulovat pouze neutrální závěr: „nelze rozhodnout bez těchto údajů“.

### O2 [major]

Prahový výnos 20–25 % ročně je stanoven bez odvození z horizontu, pravděpodobnosti úplné ztráty, alternativního výnosu, likviditní prémie nebo rizikového profilu investora. Může vést k falešné přesnosti.

Suggestion: Prahovou hodnotu odvodit z individuálního požadovaného výnosu a scénářů ztráty/likvidity; uvést IRR po poplatcích, daních a zředění včetně pravděpodobností a citlivosti.

### O3 [major]

Model založený hlavně na tržbách a výstupním násobku ignoruje ekonomiku generativní AI: hrubou marži po nákladech na inference, náklady na výpočet, kapitálové závazky, cash burn, potřebu dalšího financování a likvidační preference. U rychle rostoucí AI firmy mohou tyto položky zásadně změnit hodnotu common akcií.

Suggestion: Doplnit model o jednotkovou ekonomiku, cash flow, kapitálové potřeby, preference jednotlivých tříd akcií a scénáře dalšího zředění; valuaci posuzovat na fully diluted bázi.

### O4 [major]

Rozmezí 1–5 % likvidního jmění je příliš široké jako obecné doporučení. Pět procent v jedné neveřejné, vysoce korelované AI firmě může být pro běžného nebo nezkušeného investora nepřiměřené a může narušit likvidní rezervu.

Suggestion: Stanovit limit podle rizikového rozpočtu, celkové expozice na AI a schopnosti snést úplnou ztrátu; bez znalosti investora doporučit pouze „malou satelitní pozici“, například s konzervativním výchozím stropem pod 1 %.

