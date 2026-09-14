# Scenariomodell: regeringsbildning 2026 – formel och beräkningar

Bygger på `partisamarbete-ratingmodell-2026.md` (Del 1 samarbetsvilja, Del 3a värde, Del 3b risk; avsnitt 9 använder även Del 2 närhet och Del 4 prioritet). Framtagen 14 september 2026, reviderad samma dag efter granskning (se ändringslogg). Antagande: slutlig mandatfördelning 176/173 eller 175/174 till V+S+MP+C.

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

**Genomförbarhet** = lägsta marginal bland de partier vars ja eller tolerans krävs för att scenariot ska hålla ("krävda partier"). Vilka som är krävda följer av riksdagsaritmetiken i avsnitt 2, inte av scenariobeskrivningen. När flera partier är krävda *tillsammans* men inte var för sig (t.ex. "två av V, MP, C") räknas gruppens bidrag som marginalen hos det sist nödvändiga partiet, alltså den näst högsta marginalen i gruppen om två av tre krävs. Negativ genomförbarhet betyder att minst ett krävt parti tjänar på att fälla.

**Formateurvillkor**: den som får regeringsbildaruppdraget (största blocket, S) måste ha minst hälften av sin bästa möjliga poäng i scenariot – annars väljer S ett annat spår oavsett vad andra partier vill.

### Komponenter

| Term | Källa | Beskrivning |
|---|---|---|
| Värde(roll), Risk(roll) | Del 3a, 3b | Regering / stödparti / tolerans / opposition. Differensen = Del 3c netto för de tre grundrollerna |
| p(roll) | Parameter | Andel av egen politik partiet får igenom i rollen (tabell nedan) |
| Värde(politik) | Del 3a, kolumn "Få sin politik genomförd" | Hur högt partiet värderar sakpolitisk utdelning |
| Rödlinjestraff | Parameter R | Avdrag om scenariot bryter en uttalad röd linje |
| Del1-straff | Del 1 (1a) | `2 × max(0, 3 − Del1(X→Y))` summerat över varje Y ≠ X som är regeringsparti *eller* part i samma formella avtal som X. Varje Y räknas en gång. Fångar ovilja som inte är formell röd linje |
| Kontextjustering | Del 3b, referensram | Risk(regering) för L och KD höjs när regeringen är S-ledd, eftersom 3b är satt med Tidö som referens. Se parametertabell |
| κ | Parameter | Kostnad för ett vänsterblocksparti att aktivt rösta tillsammans med SD för att fälla en S-ledd regering. Noll för högerpartier (de behöver inte agera för att F ska inträffa) |

### Roller och p-värden

Tolerans delas i två varianter eftersom de skiljer sig i vad som krävs av partiet i budgetomröstningen (avsnitt 2):

- **Passiv tolerans**: partiet kan lägga ner rösterna i både statsministeromröstning och budgetomröstning utan att regeringen faller. Kostar oppositionens risk.
- **Aktiv tolerans**: regeringens budget saknar egen relativ majoritet, så partiet måste aktivt rösta för den varje år. Partiet bär då i praktiken ett stödpartis ansvar utan avtal, som V 2014–2018. Värde och risk sätts till medelvärdet av opposition och stödparti; p ligger mellan passiv tolerans och avtal, eftersom partiets aktiva ja ger förhandlingsutrymme budget för budget.

| Roll | p | Netto |
|---|---|---|
| Statsministerparti | 0,70 | Del 3c regering |
| Övrigt regeringsparti | 0,50 | Del 3c regering (kontextjusterad vid behov) |
| Stödparti med formellt avtal | 0,40 | Del 3c stödparti |
| Aktiv tolerans (budgetansvar utan avtal) | 0,25 | (netto opposition + netto stödparti) / 2 |
| Passiv tolerans | 0,15 | Del 3c opposition |
| Opposition | 0,05 | Del 3c opposition |
| Låsning/nyval (F) | 0,00 | Del 3c opposition − κ |

### Parametervärden

| Parameter | Värde | Motiv |
|---|---|---|
| R (rödlinjestraff) | 6 | Uttalade röda linjer: C mot V-ministrar, C mot SD-beroende regering, S mot SD, MP mot ny kärnkraft i regering |
| Risk(regering) L i S-ledd regering | 8 (3b: 4) | L har just gjort upp med M om SD i regeringen; att i stället regera med Andersson är existentiellt för både den liberala kärnan och den borgerliga basen |
| Risk(regering) KD i S-ledd regering | 7 (3b: 3) | Högerorienterad bas; KD:s öppning mot S gäller sakfrågor, inte regeringssamarbete |
| κ(V) | 3 | Att fälla Andersson med SD:s röster är svårt att förklara för basen |
| κ(MP) | 3 | Samma skäl |
| κ(C) | 1 | C har på förhand sagt nyval hellre än V – kostnaden är redan tagen |
| κ(S, L, KD, M, SD) | 0 | |

### Indata från ratingmodellen

| Parti | Netto reg | Netto stöd | Netto opp | Netto aktiv tolerans | Politik | Fallback (netto opp − κ) |
|---|---|---|---|---|---|---|
| V | +3 | −3 | +3 | 0 | 7 | 0 |
| S | +6 | −6 | 0 | −3 | 8 | 0 |
| MP | 0 | 0 | +2 | +1 | 8 | −1 |
| C | −3 | +3 | +2 | +2,5 | 7 | +1 |
| L | +4 (S-ledd: 0) | −2 | −3 | −2,5 | 6 | −3 |
| KD | +5 (S-ledd: +1) | 0 | −1 | −0,5 | 6 | −1 |
| M | +7 | −8 | −1 | −4,5 | 7 | −1 |
| SD | +1 | +5 | +6 | +5,5 | 9 | +6 |

---

## 2. Riksdagsaritmetik

Mandat vid 176/173: S 100, M 70, SD 62, V 29, C 25, KD 22, MP 22, L 19.

Två omröstningar avgör om ett scenario håller, och de har olika regler:

- **Statsministeromröstningen** (negativ parlamentarism): förslaget faller bara om minst 175 ledamöter röstar nej. Nedlagda röster hjälper regeringen. Ett parti är *individuellt krävt* om nej-sidan når 175 så snart partiet röstar nej. Partier kan också vara krävda *tillsammans*, när nej-sidan når 175 först om flera av dem röstar nej.
- **Budgetomröstningen** (rambeslutet): regeringens förslag ställs mot det motförslag som samlar flest röster. Nedlagda röster räknas inte. Regeringens ram faller om ett enda motförslag får fler röster än den. Tolerans är alltså bara passiv om regeringen och dess avtalspartier ensamma är fler än det största sammanhållna motförslaget.

| Scenario | Regering + avtal | Största motblock | Nej-sida i SM-omröstning | Individuellt krävda | Krävda tillsammans | Toleransform |
|---|---|---|---|---|---|---|
| A, B | S+MP+V+C = 176 | Tidö 173 | 173 + varje avhoppare | S, MP, V, C | – | – (alla i avtal) |
| A′, B′ | S+MP+C = 147 | Tidö 173 | 173 + V = 202 | S, MP, V, C | – | V **aktiv**: 147 < 173, V måste rösta för budgeten |
| C | S+MP+V+C = 176 | Tidö 173 | 173 + C = 198 | S, MP, V, C | – | – |
| D | S+MP+C = 147 | Tidö 173 | 173 + V = 202 | S, MP, V, C | – | V **aktiv** |
| E | S+L+KD+C = 166 | M+SD 132 | 132 + V + MP = 183; 132 + V = 161; 132 + MP = 154; 132 + C = 157 | S, L, KD | två av {V, MP, C} | V, MP **passiv**: 166 > 132 |
| G1 | M+KD+L+C = 136 | S+V+MP 151 | 151 + SD = 213; 151 + C = 176 | M, KD, L, C, SD | – | SD **aktiv**: 136 < 151 |
| G2 | M+KD+L = 111 | S 100 (eller S+V+MP 151) | 138 utan S; 238 med S | M, KD, L, S | – | S passiv i SM-omröstningen; budgeten faller om V och MP röstar på S:s ram |
| G3 | M+KD+L = 111 | S+V+MP 151 | 151 + SD = 213; 151 + C = 176 | M, KD, L, SD, C | – | SD **aktiv**, C **passiv** (räcker med SD:s ja: 173 > 151) |

Två saker följer direkt av tabellen:

1. **E kräver inte både V och MP.** M+SD har 132 mandat. Det räcker att två av V, MP och C avstår för att regeringen ska passera, och i budgetomröstningen behöver ingen av dem rösta för. E är strukturellt det stabilaste S-ledda scenariot utan formellt avtal med V.
2. **A′/B′ och D bygger på att V aktivt röstar för S-budgeten varje år.** Det är samma läge som ledde till decemberkrisen 2014. "Tolerans utan avtal" är i de scenarierna inte opposition, det är stödpartiskap utan skriftlig bindning.

Vid 175/174 ändras ingen av kvalifikationerna ovan; G1:s och G3:s beroende av C blir dock beroende av vilket parti som tappar mandatet.

---

## 3. Scenarier och roller

| Scenario | Regering | Stödparti (avtal) | Tolererar | Krävda partier (från avsnitt 2) |
|---|---|---|---|---|
| A | S (ledare), MP | V, C | – | S, MP, V, C |
| A′ | S (ledare), MP | C | V (aktiv) | S, MP, V, C |
| B | S (ledare) | MP, V, C | – | S, MP, V, C |
| B′ | S (ledare) | MP, C | V (aktiv) | S, MP, V, C |
| C | S (ledare), MP, V | C | – | S, MP, V, C |
| D | S (ledare), MP, C | – | V (aktiv) | S, MP, C, V |
| E | S (ledare), L, KD | C | MP, V (passiv) | S, L, KD + två av {C, MP, V} |
| G1 | M (ledare), KD, L, C | – | SD (aktiv) | M, KD, L, C, SD |
| G2 | M (ledare), KD, L | – | S (passiv) | M, KD, L, S |
| G3 | M (ledare), KD, L | – | SD (aktiv), C (passiv) | M, KD, L, SD, C |
| F | Nyval / låsning | – | – | – |

A′ och B′ skiljer sig från A och B enbart i att V inte binder sig i ett formellt stödpartiavtal utan förhandlar budget för budget (som 2014–2018). G3 är nytt: det är det M-ledda scenario som riksdagsaritmetiken faktiskt tillåter utan att C sitter i regeringen.

---

## 4. Beräkning per scenario

Poäng = netto(roll) + p × politik − straff. Marginal = poäng − fallback.

### A. S+MP, avtal med V och C

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| V | stöd avtal | −3 | 2,8 | 0 | −0,2 | **−0,2** |
| C | stöd avtal | +3 | 2,8 | Del1 2 (C→V = 2, avtalspart) | 3,8 | +2,8 |

Genomförbarhet: **−0,2** (V)

### A′. S+MP, avtal med C, V tolererar aktivt

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| V | aktiv tolerans | 0 | 1,75 | 0 | 1,75 | **+1,75** |
| C | stöd avtal | +3 | 2,8 | 0 | 5,8 | +4,8 |

Genomförbarhet: **+1,75** (V)

### B. S ensam, avtal med MP, V och C

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | stöd avtal | 0 | 3,2 | 0 | 3,2 | +4,2 |
| V | stöd avtal | −3 | 2,8 | 0 | −0,2 | **−0,2** |
| C | stöd avtal | +3 | 2,8 | Del1 2 (C→V = 2, avtalspart) | 3,8 | +2,8 |

Genomförbarhet: **−0,2** (V)

### B′. S ensam, avtal med MP och C, V tolererar aktivt

Som B men V i aktiv tolerans: V 1,75 / +1,75, C utan straff 5,8 / +4,8. Genomförbarhet: **+1,75** (V)

### C. S+MP+V, C stödparti

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| V | regering | +3 | 3,5 | 0 | 6,5 | +6,5 |
| C | stöd avtal | +3 | 2,8 | R 6 + Del1 2 (C→V = 2) | −2,2 | **−3,2** |

Genomförbarhet: **−3,2** (C)

### D. S+MP+C, V tolererar aktivt

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| MP | regering | 0 | 4,0 | 0 | 4,0 | +5,0 |
| C | regering | −3 | 3,5 | 0 | 0,5 | **−0,5** |
| V | aktiv tolerans | 0 | 1,75 | 0 | 1,75 | +1,75 |

Genomförbarhet: **−0,5** (C)

### E. S+L+KD, avtal med C, MP och V tolererar passivt

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| S | ledare | +6 | 5,6 | 0 | 11,6 | +11,6 |
| L | regering (kontextjusterad risk 8) | 0 | 3,0 | 0 | 3,0 | +6,0 |
| KD | regering (kontextjusterad risk 7) | +1 | 3,0 | 0 | 4,0 | +5,0 |
| C | stöd avtal | +3 | 2,8 | 0 | 5,8 | +4,8 |
| MP | passiv tolerans | +2 | 1,2 | Del1 2 (MP→KD = 2) | 1,2 | **+2,2** |
| V | passiv tolerans | +3 | 1,05 | Del1 4 (V→L = 2, V→KD = 2) | 0,05 | +0,05 |

Krävda: S, L, KD individuellt, plus två av {C, MP, V}. C (+4,8) och MP (+2,2) räcker; V behövs inte. Genomförbarhet: **+2,2** (MP)

### G1. M+KD+L+C, SD tolererar aktivt

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| M | ledare | +7 | 4,9 | 0 | 11,9 | +12,9 |
| KD | regering | +5 | 3,0 | 0 | 8,0 | +9,0 |
| L | regering | +4 | 3,0 | 0 | 7,0 | +10,0 |
| C | regering | −3 | 3,5 | R 6 (SD-beroende) | −5,5 | **−6,5** |
| SD | aktiv tolerans | +5,5 | 2,25 | Del1 4 (SD→C = 1) | 3,75 | −2,25 |

Genomförbarhet: **−6,5** (C)

### G2. M+KD+L, S tolererar passivt

S: 0 + 1,2 = 1,2, marginal +1,2. M 11,9, KD 8,0, L 7,0. Genomförbarhet +1,2 – **men faller på formateurvillkoret**: S:s poäng 1,2 är långt under hälften av S:s bästa (11,6).

### G3. M+KD+L, SD tolererar aktivt och C passivt

| Parti | Roll | Netto | p×politik | Straff | Poäng | Marginal |
|---|---|---|---|---|---|---|
| M | ledare | +7 | 4,9 | 0 | 11,9 | +12,9 |
| KD | regering | +5 | 3,0 | 0 | 8,0 | +9,0 |
| L | regering | +4 | 3,0 | 0 | 7,0 | +10,0 |
| SD | aktiv tolerans | +5,5 | 2,25 | 0 | 7,75 | +1,75 |
| C | passiv tolerans | +2 | 1,05 | R 6 (SD-beroende) | −2,95 | **−3,95** |

Genomförbarhet: **−3,95** (C). Bättre än G1 men fortfarande negativt: C:s röda linje mot SD-beroende regeringar räcker ensam för att stoppa alla M-ledda spår så länge C står fast.

---

## 5. Sammanställning

| Scenario | Genomförbarhet | Bindande parti | Formateurvillkor | Toleransform |
|---|---|---|---|---|
| E | +2,2 | MP | ok | passiv |
| A′ | +1,75 | V | ok | aktiv |
| B′ | +1,75 | V | ok | aktiv |
| G2 | +1,2 | S | **faller** | passiv |
| A | −0,2 | V | ok | – |
| B | −0,2 | V | ok | – |
| D | −0,5 | C | ok | aktiv |
| C | −3,2 | C | ok | – |
| G3 | −3,95 | C | ok | aktiv/passiv |
| G1 | −6,5 | C | ok | aktiv |
| F | 0 (definition) | – | – | – |

### Känslighet

| Ändring | Effekt |
|---|---|
| Tolerans behandlas som passiv överallt (modellens ursprungsversion) | A′/B′ stiger till +4,05 och går om E. Skillnaden mot A/B blir 4,25 i stället för 1,95 |
| κ = 0 för V och MP | V:s fallback blir +3, MP:s +2. A′/B′ faller till −1,25, E till −0,8 (MP), A/B till −3,2. Inget S-lett scenario är då genomförbart och F vinner. κ är modellens mest avgörande parameter |
| L och KD utan kontextjustering (3b-värden rakt av) | L +10,0 och KD +9,0 i E. Genomförbarheten är oförändrad (+2,2, MP), men E:s robusthet mot förändringar hos L och KD överskattas |
| p(aktiv tolerans) 0,25 → 0,15 | A′/B′ faller till +1,05, fortfarande över A/B men under E |
| Del1-straff enbart mot regeringspartier (ursprungsversion) | C stiger till +4,8 i A och B. Ingen effekt på genomförbarhet, som bestäms av V |

### Vad formeln säger

1. **E är det scenario som klarar sig bäst på egna meriter, och av strukturella skäl.** Regeringen S+L+KD med C-avtal har relativ majoritet i budgetomröstningen mot M+SD och behöver bara två av V, MP och C i statsministeromröstningen. C och MP räcker; V:s hållning spelar ingen roll. Priset är att L och KD måste korsa blockgränsen dagen efter ett val där de gick fram med M och SD, och kontextjusteringen av deras risk är en gissning.
2. **V:s problem är fortfarande avtalsformen, men gapet är mindre än först beräknat.** V som formellt stödparti (A, B) ligger vid noll; V i aktiv tolerans (A′, B′) ligger på +1,75. Skillnaden är stödpartiets risk 7 mot toleransens 4,5. Modellen förutspår att V kräver antingen ministerposter eller ingen formell bindning, men A′/B′ ger S en regering som varje år hänger på V:s aktiva ja i budgetomröstningen.
3. **S:s stabilitetsbehov och riksdagsaritmetiken pekar åt samma håll.** S:s poäng är identisk i A och A′, men efter avsnitt 2 är A′ en decemberkris i väntan. Det gör E och A/B mer attraktiva för S än poängen visar.
4. **C blockerar allt där C sitter i regering eller V har ministrar.** C:s regeringsnetto −3 gör D omöjligt även utan röd linje. C:s bästa utfall är stödparti i alla S-ledda scenarier, och C är ett av två räckande partier i E.
5. **Ingen M-ledd lösning klarar båda villkoren.** G1 och G3 faller på C:s röda linje mot SD-beroende, G2 på formateurvillkoret. G3 visar att avståndet är mindre än G1 antydde (−3,95 mot −6,5), men det är fortfarande C:s röda linje, inte poängen, som avgör.

---

## 6. Sannolikhetsbedömning

Formeln ger en rangordning, inte sannolikheter. Sannolikheterna nedan är bedömda med formelns resultat som huvudinput, korrigerade för hålen i avsnitt 7.

| Scenario | 176/173 | 175/174 | Motiv |
|---|---|---|---|
| **A′ + B′** (S ± MP, C-avtal, V tolererar aktivt) | 30 % | 27 % | Genomförbart, men S vet att budgeten hänger på V varje år. Sänks från tidigare 40 % |
| **A + B** (S ± MP, formellt avtal med V och C) | 24 % | 22 % | Formeln säger knivsegg för V; S:s stabilitetsbehov driver ändå hit |
| **E** (S+L+KD, C-avtal, MP och V tolererar passivt) | 22 % | 25 % | Modellens topp och strukturellt stabilast. Hålls nere av att L:s och KD:s vilja är obevisad. Stiger vid 175 när S söker marginal |
| **D** (S+MP+C, V tolererar aktivt) | 4 % | 4 % | C:s regeringsnetto −3 |
| **C** (S+MP+V, C stöd) | 3 % | 3 % | Röd linje + Del1 |
| **F** (nyval/låsning) | 13 % | 15 % | |
| **G1 + G2 + G3** (M-ledd utan nyval) | 4 % | 4 % | |

Aggregerat: S-ledd regering direkt 83 % / 81 %; V utanför regeringen 80 % / 78 %; V utan formellt avtal (A′, B′, E, D) 56 % / 56 %.

---

## 7. Kända begränsningar

- **Fallback är alltid F.** I verkligheten jämför varje parti med sitt bästa *tillgängliga* alternativ, inte med nyval. Formateurvillkoret är en grov approximation av detta för S.
- **Aktiv tolerans är fortfarande ett medelvärde.** Att V:s risk i A′ är 4,5 och inte 7 bygger på att "utan avtal" ger V en synlig frihet gentemot basen. Om basen inte ser skillnaden är A′ = A.
- **Budgetaritmetiken antar sammanhållna motblock.** Att Tidö lägger en gemensam ram i opposition är troligt; att S+V+MP gör det mot en M-regering (G3) är mindre säkert. Toleransformen i G-scenarierna är därför osäkrare än i S-scenarierna.
- **Kontextjusteringen för L och KD är gissad**, liksom att S:s regeringsrisk 4 inte påverkas av att regera med L och KD i stället för med MP.
- **p-värdena är gissade.** Politikandelen per roll är den känsligaste parametern efter κ; se känslighetstabellen.
- **Del 3-siffrorna är subjektiva** och dessutom skrivna innan valresultatet var känt. V:s regeringsvärde 8 kan ha stigit med +5 mandat.
- **Politiktermen är scenariooberoende i grundformeln.** Avsnitt 9 visar vad som händer när den skalas med prioritetsviktad närhet; rangordningen står sig.
- **Inga andra interaktionseffekter.** Kontextjusteringen täcker bara L och KD i S-ledd regering. Motsvarande justering för t.ex. C i en M-ledd regering (G1) är inte gjord.

---

## 8. Uppdateringspunkter

1. Slutlig mandatfördelning.
2. V:s första besked om formen för samarbete (avtal / ministerposter / inget).
3. Om KD eller L offentligt öppnar för Andersson – höjer E ytterligare. Om de stänger dörren – E går till nära noll och A′/B′ och A/B tar över.
4. Vikta om Del 3 efter valresultatet innan nästa körning.

## 9. Eftergifter per scenario (Del 4)

Del 2 säger hur nära partierna står; Del 4 säger hur mycket varje område betyder för respektive parti. Kombinerat ger de en **prioritetsviktad närhet** per parti och scenario: hur stor del av det partiet bryr sig om som överlever i uppgörelsen.

```
Närhet_P(X, scenario) = Σ_k Prioritet(X, k) × N_k(X, krets) / Σ_k Prioritet(X, k)
N_k(X, krets)         = mandatviktat medel av Del 2-närhet(X, Y, k) över Y i kretsen, Y ≠ X
```

*Kretsen* är regeringspartierna plus partier med formellt avtal, alltså de som förhandlar plattformen. Tolererande partier räknas mot kretsen men ingår inte i den. *Dyraste eftergifter* = de tre områden där Prioritet × (10 − N_k) är störst, alltså där partiet både bryr sig och står långt från kretsen.

### 9a. Prioritetsviktad närhet och dyraste eftergifter

**A. S+MP, avtal med V och C** (krets S+MP+V+C)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| S | regering | 5,37 | Rättsväsende, Migration, Arbetsmarknad |
| MP | regering | 5,76 | Energi, Klimat, Migration |
| V | stöd avtal | 5,49 | Bostad, Skatter, Utrikes |
| C | stöd avtal | 4,68 | Landsbygd, Arbetsmarknad, Skatter |

**A′. S+MP, avtal med C, V tolererar aktivt** (krets S+MP+C)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| S | regering | 5,26 | Arbetsmarknad, Rättsväsende, Välfärd |
| MP | regering | 5,55 | Energi, Klimat, Migration |
| C | stöd avtal | 5,02 | Landsbygd, Arbetsmarknad, Skatter |
| V | aktiv tolerans | 5,49 | Bostad, Skatter, Utrikes |

**C. S+MP+V, C stödparti** (krets S+MP+V+C)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| S | regering | 5,37 | Rättsväsende, Migration, Arbetsmarknad |
| MP | regering | 5,76 | Energi, Klimat, Migration |
| V | regering | 5,49 | Bostad, Skatter, Utrikes |
| C | stöd avtal | 4,68 | Landsbygd, Arbetsmarknad, Skatter |

**D. S+MP+C, V tolererar aktivt** (krets S+MP+C)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| S | regering | 5,26 | Arbetsmarknad, Rättsväsende, Välfärd |
| MP | regering | 5,55 | Energi, Klimat, Migration |
| C | regering | 5,02 | Landsbygd, Arbetsmarknad, Skatter |
| V | aktiv tolerans | 5,49 | Bostad, Skatter, Utrikes |

**E. S+L+KD, avtal med C, MP och V tolererar passivt** (krets S+L+KD+C)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| S | regering | 4,93 | Arbetsmarknad, Välfärd, Skatter |
| L | regering | 5,73 | Skola, Skatter, Utrikes |
| KD | regering | 5,20 | Värderingar, Välfärd, Skatter |
| C | stöd avtal | 5,32 | Landsbygd, Arbetsmarknad, Skatter |
| MP | passiv tolerans | 4,97 | Energi, Klimat, Migration |
| V | passiv tolerans | 4,50 | Bostad, Skatter, Fördelning |

**G1. M+KD+L+C, SD tolererar aktivt** (krets M+KD+L+C)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| M | regering | 7,33 | Migration, Rättsväsende, Integration |
| KD | regering | 7,11 | Värderingar, Välfärd, Migration |
| L | regering | 7,31 | Värderingar, Skola, Klimat |
| C | regering | 6,37 | Migration, Klimat, Landsbygd |
| SD | aktiv tolerans | 5,51 | EU, Integration, Migration |

**G2. M+KD+L, S tolererar passivt** (krets M+KD+L)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| M | regering | 7,94 | Migration, Skatter, Värderingar |
| KD | regering | 7,56 | Värderingar, Välfärd, Fördelning |
| L | regering | 7,44 | Värderingar, Skola, Klimat |
| S | passiv tolerans | 4,83 | Arbetsmarknad, Välfärd, Fördelning |

**G3. M+KD+L, SD tolererar aktivt och C passivt** (krets M+KD+L)

| Parti | Roll | Närhet_P | Dyraste eftergifter |
|---|---|---|---|
| M | regering | 7,94 | Migration, Skatter, Värderingar |
| KD | regering | 7,56 | Värderingar, Välfärd, Fördelning |
| L | regering | 7,44 | Värderingar, Skola, Klimat |
| SD | aktiv tolerans | 6,04 | EU, Välfärd, Fördelning |
| C | passiv tolerans | 6,37 | Migration, Klimat, Landsbygd |

B och B′ har samma krets som A respektive A′ och därmed samma värden; MP:s roll ändrar inte kretsen.

Vad tabellerna säger:

- **C är det parti som ger upp mest i alla S-ledda scenarier** (Närhet_P 4,7–5,3). Priset är landsbygd, arbetsmarknad och skatter, aldrig klimat. Det är den lista S bör ha framför sig när C:s avtal förhandlas.
- **S ger upp mer i E än i A** (4,93 mot 5,37). Med L och KD i regeringen är det arbetsmarknad, välfärd och skatter som kostar, alltså S:s egna kärnområden. Poängformeln fångar det bara via Del 3.
- **KD:s dyraste område är värderingsfrågor i varje konstellation**, även i Tidö (G1–G3). Det är ett problem KD har med L, inte med S.
- **V:s prioriteter passar S bättre än Del 2 visar.** V:s dyraste eftergifter i A är bostad, skatter och utrikes, alla med måttlig prioritet. Migration och rättsväsende, där V–S-avståndet är störst, syns inte på listan eftersom V prioriterar dem lågt.
- **MP:s kostnad är alltid energi och klimat**, oavsett scenario. I E stiger den (Närhet_P 4,97) eftersom L och KD är kärnkraftspartier. MP:s passiva tolerans i E är billigare i Del 3-termer men dyrare i sak.
- **C i Tidö (G1) betalar med migration, klimat och landsbygd**, vilket är exakt de tre områden C lämnade Alliansen över. SD:s kostnad i G1 och G3 är EU, integration och migration: SD tolererar en regering som är för mjuk på SD:s kärnområden.

### 9b. Formel v2: politikutdelning skalad med Närhet_P

I grundformeln (avsnitt 1) är politiktermen `p(roll) × Värde(politik)`, oberoende av vilka partiet gör upp med. I v2 skalas den med hur mycket av partiets prioriterade politik som faktiskt överlever i kretsen:

```
Politikterm v2 = p(roll) × Värde(politik) × Närhet_P(X, scenario) / 10
```

Allt annat är oförändrat. Eftersom Närhet_P ligger på 4,5–8 halveras ungefär politiktermen för S-ledda scenarier och minskar med en fjärdedel för Tidö-scenarier.

| Scenario | Genomförbarhet v1 | Genomförbarhet v2 | Bindande parti | Formateurvillkor |
|---|---|---|---|---|
| E | +2,20 (MP) | +1,60 (MP) | MP | ok |
| A′ | +1,75 (V) | +0,96 (V) | V | ok |
| B′ | +1,75 (V) | +0,96 (V) | V | ok |
| G2 | +1,20 (S) | +0,58 (S) | S | **faller** |
| A | −0,20 (V) | −1,46 (V) | V | ok |
| B | −0,20 (V) | −1,46 (V) | V | ok |
| D | −0,50 (C) | −2,24 (C) | C | ok |
| G3 | −3,95 (C) | −4,33 (C) | C | ok |
| C | −3,20 (C) | −4,69 (C) | C | ok |
| G1 | −6,50 (C) | −7,77 (C) | C | ok |

Rangordningen är oförändrad i toppen: E, sedan A′/B′, sedan A/B. Tre saker ändras:

1. **Alla marginaler krymper**, eftersom fallback F inte har någon politikterm att skala. Gapet mellan E och A′/B′ växer från 0,45 till 0,64, och A/B går från knivsegg (−0,2) till klart negativt (−1,46) för V. V2 gör alltså V:s ovilja mot ett formellt avtal tydligare, inte svagare.
2. **V faller under noll även i E** (−0,53), men det spelar ingen roll eftersom C och MP räcker. Hade V varit individuellt krävt i E skulle v2 ha vänt resultatet. Riksdagsaritmetiken i avsnitt 2 bär mer av E:s genomförbarhet än poängen gör.
3. **G3 går om C** i rangordning (−4,33 mot −4,69). Ingen praktisk betydelse, båda faller, men det visar att S+MP+V-regeringen är ännu sämre för C när C:s prioriteter vägs in.

V2 är inte huvudformeln, eftersom den lägger en gissad matris (Del 4) ovanpå en annan gissad matris (Del 2) och mandatviktar avstånd inom kretsen på ett sätt som inte fångar att ett litet parti kan ha veto på sitt profilområde. Den är en robusthetskontroll: grundformelns rangordning överlever när politikutdelningen görs scenarioberoende.

---

## Ändringslogg

- 2026-09-14: Ursprunglig version med scenarierna A–G2 och F.
- 2026-09-14 (granskning, prioritet): Avsnitt 9 tillagt: prioritetsviktad närhet och dyraste eftergifter per parti och scenario (9a) samt formel v2 med scenarioberoende politikterm (9b). Begränsningar uppdaterade.
- 2026-09-14 (granskning): Riksdagsaritmetik tillagd (avsnitt 2); krävda partier härleds nu från mandaten. E:s genomförbarhet rättad från +0,05 (V) till +2,2 (MP) eftersom V och MP inte är krävda var för sig. Tolerans delad i aktiv och passiv; V i A′, B′ och D är aktiv (147 < 173 i budgetomröstningen). Kontextjusterad regeringsrisk för L (8) och KD (7) i S-ledd regering. Del1-straff gäller nu även avtalspartner, vilket ger C ett straff i A och B. Scenario G3 tillagt. Känslighetstabell tillagd. Sannolikheter omräknade; aggregatet "V utan formellt avtal" inkluderar nu D.
