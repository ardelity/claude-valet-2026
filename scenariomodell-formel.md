# Scenariomodell: regeringsbildning 2026 – formel och beräkningar

Bygger på `partisamarbete-ratingmodell-2026.md` (Del 1 samarbetsvilja, Del 3a värde, Del 3b risk). Framtagen 14 september 2026. Antagande: slutlig mandatfördelning 176/173 eller 175/174 till V+S+MP+C.

---

## 1. Formel

För varje scenario får varje parti en **roll** och en **politikandel**. Partiets poäng i scenariot:

```
Poäng(parti, scenario) = Värde(roll) − Risk(roll)
                       + p(roll) × Värde(politik)
                       − Rödlinjestraff
                       − Del1-straff
```

**Marginal** = Poäng(scenario) − Poäng(fallback), där fallback är scenario F (nyval/låsning).

```
Fallback(parti) = Värde(opposition) − Risk(opposition) − κ(parti)
```

**Genomförbarhet** = lägsta marginal bland de partier vars ja eller tolerans krävs för att scenariot ska hålla ("krävda partier"). Negativ genomförbarhet betyder att minst ett krävt parti tjänar på att fälla.

**Formateurvillkor**: den som får regeringsbildaruppdraget (största blocket, S) måste ha minst hälften av sin bästa möjliga poäng i scenariot – annars väljer S ett annat spår oavsett vad andra partier vill.

### Komponenter

| Term | Källa | Beskrivning |
|---|---|---|
| Värde(roll), Risk(roll) | Del 3a, 3b | Regering / stödparti / opposition. Differensen = Del 3c netto |
| p(roll) | Parameter | Andel av egen politik partiet får igenom i rollen (tabell nedan) |
| Värde(politik) | Del 3a, kolumn "Få sin politik genomförd" | Hur högt partiet värderar sakpolitisk utdelning |
| Rödlinjestraff | Parameter R | Avdrag om scenariot bryter en uttalad röd linje |
| Del1-straff | Del 1 (1a) | `2 × max(0, 3 − Del1(X→Y))` summerat över varje regeringsparti Y ≠ X. Fångar ovilja som inte är formell röd linje |
| κ | Parameter | Kostnad för ett vänsterblocksparti att aktivt rösta tillsammans med SD för att fälla en S-ledd regering. Noll för högerpartier (de behöver inte agera för att F ska inträffa) |

### Parametervärden

| Roll | p |
|---|---|
| Statsministerparti | 0,70 |
| Övrigt regeringsparti | 0,50 |
| Stödparti med formellt avtal | 0,40 |
| Tolererar utan avtal (budgetsamarbete från fall till fall) | 0,15 |
| Opposition | 0,05 |
| Låsning/nyval (F) | 0,00 |

| Parameter | Värde | Motiv |
|---|---|---|
| R (rödlinjestraff) | 6 | Uttalade röda linjer: C mot V-ministrar, C mot SD-beroende regering, S mot SD, MP mot ny kärnkraft i regering |
| κ(V) | 3 | Att fälla Andersson med SD:s röster är svårt att förklara för basen |
| κ(MP) | 3 | Samma skäl |
| κ(C) | 1 | C har på förhand sagt nyval hellre än V – kostnaden är redan tagen |
| κ(S, L, KD, M, SD) | 0 | |

### Indata från ratingmodellen

| Parti | Netto reg | Netto stöd | Netto opp | Politik | Fallback (netto opp − κ) |
|---|---|---|---|---|---|
| V | +3 | −3 | +3 | 7 | 0 |
| S | +6 | −6 | 0 | 8 | 0 |
| MP | 0 | 0 | +2 | 8 | −1 |
| C | −3 | +3 | +2 | 7 | +1 |
| L | +4 | −2 | −3 | 6 | −3 |
| KD | +5 | 0 | −1 | 6 | −1 |
| M | +7 | −8 | −1 | 7 | −1 |
| SD | +1 | +5 | +6 | 9 | +6 |

---

## 2. Scenarier och roller

| Scenario | Regering | Stödparti (avtal) | Tolererar | Krävda partier |
|---|---|---|---|---|
| A | S (ledare), MP | V, C | – | S, MP, V, C |
| A′ | S (ledare), MP | C | V | S, MP, V, C |
| B | S (ledare) | MP, V, C | – | S, MP, V, C |
| B′ | S (ledare) | MP, C | V | S, MP, V, C |
| C | S (ledare), MP, V | C | – | S, MP, V, C |
| D | S (ledare), MP, C | – | V | S, MP, C, V |
| E | S (ledare), L, KD | C | MP, V | S, L, KD, C, MP, V |
| G1 | M (ledare), KD, L, C | – | SD | M, KD, L, C, SD |
| G2 | M (ledare), KD, L | – | S | M, KD, L, S |
| F | Nyval / låsning | – | – | – |

A′ och B′ är nya i förhållande till den tidigare analysen: de skiljer sig från A och B enbart i att V inte binder sig i ett formellt stödpartiavtal utan förhandlar budget för budget (som 2014–2018).

---

## 3. Beräkning per scenario

Poäng = netto(roll) + p × politik − straff. Marginal = poäng − fallback.

### A. S+MP, avtal med V och C

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| V | stöd avtal | −3 | 2,8 | 0 | −0,2 | **−0,2** |
| C | stöd avtal | +3 | 2,8 | 0 | 5,8 | +4,8 |

Genomförbarhet: **−0,2** (V)

### A′. S+MP, avtal med C, V tolererar

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| V | tolererar | +3 | 1,05 | 0 | 4,05 | **+4,05** |
| C | stöd avtal | +3 | 2,8 | 0 | 5,8 | +4,8 |

Genomförbarhet: **+4,05** (V)

### B. S ensam, avtal med MP, V och C

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | stöd avtal | 0 | 3,2 | 0 | 3,2 | +4,2 |
| V | stöd avtal | −3 | 2,8 | 0 | −0,2 | **−0,2** |
| C | stöd avtal | +3 | 2,8 | 0 | 5,8 | +4,8 |

Genomförbarhet: **−0,2** (V)

### B′. S ensam, avtal med MP och C, V tolererar

Som B men V tolererar: V 4,05 / +4,05. Genomförbarhet: **+4,05** (V)

### C. S+MP+V, C stödparti

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| V | regering | +3 | 3,5 | 0 | 6,5 | +6,5 |
| C | stöd avtal | +3 | 2,8 | R 6 + Del1 2 (C→V = 2) | −2,2 | **−3,2** |

Genomförbarhet: **−3,2** (C)

### D. S+MP+C, V tolererar

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| C | regering | −3 | 3,5 | 0 | 0,5 | **−0,5** |
| V | tolererar | +3 | 1,05 | 0 | 4,05 | +4,05 |

Genomförbarhet: **−0,5** (C)

### E. S+L+KD, avtal med C, MP och V tolererar

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| L | regering | +4 | 3,0 | 0 | 7,0 | +10,0 |
| KD | regering | +5 | 3,0 | 0 | 8,0 | +9,0 |
| C | stöd avtal | +3 | 2,8 | 0 | 5,8 | +4,8 |
| MP | tolererar | +2 | 1,2 | Del1 2 (MP→KD = 2) | 1,2 | +2,2 |
| V | tolererar | +3 | 1,05 | Del1 4 (V→L = 2, V→KD = 2) | 0,05 | **+0,05** |

Genomförbarhet: **+0,05** (V)

### G1. M+KD+L+C, SD tolererar

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| M | ledare | +7 | 4,9 | 0 | 11,9 | +12,9 |
| KD | regering | +5 | 3,0 | 0 | 8,0 | +9,0 |
| L | regering | +4 | 3,0 | 0 | 7,0 | +10,0 |
| C | regering | −3 | 3,5 | R 6 (SD-beroende) | −5,5 | **−6,5** |
| SD | tolererar | +6 | 1,35 | Del1 4 (SD→C = 1) | 3,35 | −2,65 |

Genomförbarhet: **−6,5** (C)

### G2. M+KD+L, S tolererar

S: +0 + 1,2 = 1,2, marginal +1,2. M 11,9, KD 8,0, L 7,0. Genomförbarhet +1,2 – **men faller på formateurvillkoret**: S:s poäng 1,2 är långt under hälften av S:s bästa (11,6).

---

## 4. Sammanställning

| Scenario | Genomförbarhet | Bindande parti | Formateurvillkor |
|---|---|---|---|
| A′ | +4,05 | V | ok |
| B′ | +4,05 | V | ok |
| E | +0,05 | V | ok |
| A | −0,2 | V | ok |
| B | −0,2 | V | ok |
| D | −0,5 | C | ok |
| G2 | +1,2 | S | **faller** |
| C | −3,2 | C | ok |
| G1 | −6,5 | C | ok |
| F | 0 (definition) | – | – |

### Vad formeln säger

1. **V:s problem är avtalsformen, inte rollen.** V som formellt stödparti (A, B) ligger vid noll; V som tolererande opposition utan avtal (A′, B′) ligger på +4. Skillnaden är helt Del 3b: stödpartirisk 7 mot oppositionsrisk 2. Modellen förutspår att V kommer att kräva antingen ministerposter eller *ingen* formell bindning – aldrig ett januariavtal.
2. **S vill det motsatta.** S:s poäng är identisk i A och A′, men A′ ger S en regering som kan förlora varje enskild budgetomröstning. Formeln fångar inte S:s behov av stabilitet – det är ett känt hål (se avsnitt 6).
3. **C blockerar allt där C sitter i regering eller V har ministrar.** C:s regeringsnetto −3 gör D omöjligt även utan röd linje. C:s bästa utfall är stödparti i alla S-ledda scenarier.
4. **E är genomförbar men hänger på V:s tolerans med marginal 0,05.** Del1-straffet mot L och KD äter upp nästan hela V:s oppositionsfördel.
5. **Ingen M-ledd lösning klarar båda villkoren.** G1 faller på C, G2 på formateurvillkoret.

---

## 5. Sannolikhetsbedömning

Formeln ger en rangordning, inte sannolikheter. Sannolikheterna nedan är bedömda med formelns resultat som huvudinput, korrigerade för hålen i avsnitt 6.

| Scenario | 176/173 | 175/174 | Motiv |
|---|---|---|---|
| **A′ + B′** (S ± MP, C-avtal, V tolererar utan formellt avtal) | 40 % | 36 % | Modellens klara topp. Sänks något för att S vill ha bindning |
| **A + B** (S ± MP, formellt avtal med V och C) | 22 % | 20 % | Formeln säger knivsegg för V; S:s stabilitetsbehov driver ändå hit |
| **E** (S+L+KD, C-avtal, MP och V tolererar) | 14 % | 17 % | Genomförbar men V-marginal ≈ 0. Stiger vid 175 när S söker marginal |
| **D** (S+MP+C, V tolererar) | 4 % | 4 % | C:s regeringsnetto −3 |
| **C** (S+MP+V, C stöd) | 3 % | 3 % | Röd linje + Del1 |
| **F** (nyval/låsning) | 13 % | 16 % | |
| **G1 + G2** (M-ledd utan nyval) | 4 % | 4 % | |

Aggregerat: S-ledd regering direkt 83 % / 80 %; V utanför regeringen 80 % / 77 %; V utan formellt avtal 54 % / 53 %.

---

## 6. Kända begränsningar

- **Stabilitetsvärde saknas.** Formeln värderar inte att S och MP föredrar en bunden majoritet framför tolerans. Det gör att A′/B′ överskattas relativt A/B. Kan åtgärdas med en term `+ s × (antal mandat bakom formellt avtal − 175)` för regeringspartier.
- **Fallback är alltid F.** I verkligheten jämför varje parti med sitt bästa *tillgängliga* alternativ, inte med nyval. Formateurvillkoret är en grov approximation av detta för S.
- **p-värdena är gissade.** Politikandelen per roll är den känsligaste parametern: p(tolerans) 0,15 → 0,30 lyfter A′/B′ ytterligare; 0,15 → 0,05 gör V indifferent mellan A och A′.
- **Del 3-siffrorna är subjektiva** och dessutom skrivna innan valresultatet var känt. V:s regeringsvärde 8 kan ha stigit med +5 mandat.
- **Inga interaktionseffekter.** Att L går in i en S-ledd regering (E) påverkar rimligen L:s risk mer än vad 3b anger, eftersom 3b är skriven med Tidö-regering som referens.

---

## 7. Uppdateringspunkter

1. Slutlig mandatfördelning.
2. V:s första besked om formen för samarbete (avtal / ministerposter / inget).
3. Om KD eller L offentligt öppnar för Andersson – höjer E.
4. Vikta om Del 3 efter valresultatet innan nästa körning.
