---
title: Handleiding
---

## ErgoTimer — Handleiding

## Inhoudsopgave

1. [Overzicht](#1-overzicht)
2. [Hoofdscherm](#2-hoofdscherm)
3. [Instellingen](#3-instellingen)
   - 3.1 [Basisschema](#31-basisschema)
   - 3.2 [Pauzes & herstel](#32-pauzes--herstel)
   - 3.3 [Meldingen](#33-meldingen)
   - 3.4 [Interface](#34-interface)
   - 3.5 [Geavanceerd](#35-geavanceerd)
4. [Schemaweergave](#4-schemaweergave)
5. [Bediening actieve taak](#5-bediening-actieve-taak)
6. [Het schema aanpassen](#6-het-schema-aanpassen)
7. [Mentale batterij](#7-mentale-batterij)
8. [Meldingen](#8-meldingen)
9. [Planningslogica](#9-planningslogica)
10. [Taaktypes](#10-taaktypes)
11. [Talen](#11-talen)

---

## 1. Overzicht

ErgoTimer is een dagelijks schemabeheerprogramma ontworpen voor mensen met Niet-Aangeboren Hersenletsel (NAH) en iedereen die zorgvuldig een balans moet bewaken tussen mentaal werk, fysieke activiteit en rust. De app genereert een persoonlijk dagschema en begeleidt je door elke taak met timers, alarmen en meldingen.

Alle gegevens worden lokaal op je apparaat opgeslagen. ErgoTimer maakt geen gebruik van internet, cloudservices of externe verbindingen.

---

## 2. Hoofdscherm

Wanneer je ErgoTimer opent, toont het hoofdscherm:

- **Bovenste gebied** — de huidige actieve taak (alleen zichtbaar wanneer de dag is gestart)
- **Schemalijst** — alle taken voor de dag in chronologische volgorde
- **Werkbalk** — instellingenpictogram (⚙️) rechtsboven

### Voor het starten

Wanneer er nog geen schema is gegenereerd, toont het scherm:
- Een prompt om een schema te configureren en te genereren
- Een knop **Schema configureren & genereren** die de instellingen opent

### Na het genereren van een schema

Zodra een schema is gegenereerd, toont het scherm de volledige dag in een kleurgecodeerde lijst. Onderaan verschijnen drie actieknoppen in één rij:
- **Taak toevoegen** — voeg handmatig een taak toe aan je schema
- **Nu Inhaken** — spring in op het huidige punt van het bestaande schema op basis van de huidige tijd
- **Herstart** — herstart vanaf de eerste taak en verschuif het hele schema naar "nu" (afgerond naar beneden op 10 minuten)

---

## 3. Instellingen

Open de instellingen door op het pictogram **⚙️** rechtsboven in het hoofdscherm te tikken. Instellingen zijn georganiseerd in inklapbare secties. Tik op een sectieheader om deze in of uit te klappen. Tik op **Schema genereren** onderaan om je instellingen toe te passen en een nieuw schema aan te maken.

### 3.1 Basisschema

#### Totaal werkuren
**Bereik:** 1 uur tot 9 uur, in stappen van 0,5 uur  
**Standaard:** 4 uur

Het totale aantal uren mentaal werk dat in de dag wordt ingepland. Fysieke pauzes, rustmomenten, fietsritten en lunch tellen niet mee — alleen mentale taken.

#### Maximale duur mentale taak
**Bereik:** 30 minuten tot 180 minuten (3 uur), in stappen van 30 minuten  
**Standaard:** 120 minuten (2 uur)

De maximale aaneengesloten duur van één mentale taak. Wanneer een mentale taak deze limiet bereikt, zal de planner altijd een pauze invoegen voor verdere mentale arbeid wordt toegestaan. Dit is een harde limiet — geen enkele mentale taak in het gegenereerde schema zal deze waarde overschrijden.

#### Minimale duur fysieke taak
**Bereik:** 5 minuten tot 60 minuten, in stappen van 5 minuten  
**Standaard:** 15 minuten

De minimale lengte van een fysieke of rustpauze ingevoegd tussen mentale taken. Dit wordt gebruikt als basiswaarde — de werkelijke pauzelengtes worden berekend met de verhouding beschreven in [Sectie 9](#9-planningslogica).

#### Begintijd
De tijd waarop je werkdag begint. Stel het uur en de minuut in met de tijdkiezer. Als een fietsrit voor het werk is geconfigureerd, begint de fietsrit op dit tijdstip en begint de eerste mentale taak nadat de fietsrit is afgelopen.

---

### 3.2 Pauzes & herstel

#### Lunchpauze
**Standaard:** Uit

Zet aan om een vaste lunchpauze in je schema op te nemen. Wanneer ingeschakeld, stel in:

- **Lunchstart** — de tijd waarop de lunch begint (bijv. 12:30)
- **Lunceinde** — de tijd waarop de lunch eindigt (bijv. 13:00)

Lunch is een vast ankerpunt in het schema. Het kan niet worden verplaatst door taakaanpassingen. Wanneer een mentale taak de lunchtijd zou overlappen, wordt deze automatisch gesplitst. Na het einde van de lunch wordt automatisch een rustperiode van 30 minuten ingevoegd.

#### Fietsrit voor het werk
**Bereik:** 0 tot 60 minuten, in stappen van 5 minuten  
**Standaard:** 0 (uitgeschakeld)

Als dit op een waarde groter dan 0 is ingesteld, wordt aan het begin van het schema een fietsrijtaak toegevoegd die begint op de geconfigureerde begintijd. De eerste mentale taak begint nadat de fietsrit is afgelopen.

#### Fietsrit na het werk
**Bereik:** 0 tot 60 minuten, in stappen van 5 minuten  
**Standaard:** 0 (uitgeschakeld)

Als dit op een waarde groter dan 0 is ingesteld, wordt aan het einde van het schema een fietsrijtaak toegevoegd, na alle mentale taken en rustpauzes.

---

### 3.3 Meldingen

#### Geluidsalarm bij taakeinde
**Standaard:** Aan

Wanneer ingeschakeld, speelt er een hoorbaar alarm wanneer de afteltimer van een taak nul bereikt. Wanneer uitgeschakeld, eindigt de taak geruisloos (er wordt nog steeds een melding getoond).

#### Alarmtoon
Selecteer welk geluid er afspeelt wanneer een taak eindigt. Tik op de keuzelijst om te kiezen uit de beschikbare opties. Gebruik de knop **Geluid testen** om een voorbeeld te horen van het geselecteerde geluid.

#### Micropauzeherinnering
**Bereik:** Uit, 5 tot 60 minuten in stappen van 5 minuten  
**Standaard:** Uit

Wanneer ingeschakeld, verschijnt tijdens mentale taken op het opgegeven interval een herinneringsmelding. Als dit bijvoorbeeld op 30 minuten is ingesteld, verschijnt er 30 minuten nadat een mentale taak is begonnen een herinnering die aanmoedigt tot een korte pauze (zoals het zetten van koffie). Micropauzes zijn geen aparte geplande taken — het zijn herinneringen binnen de huidige taak.

---

### 3.4 Interface

#### Taal
Kies tussen **Engels** en **Nederlands**. De app toont alle tekst in de geselecteerde taal.

#### Interfacemodus
**Standaard:** Rustig

ErgoTimer biedt drie interfacemodi:
- **Standaard** — alle details zichtbaar, knoppen altijd weergegeven
- **Rustig** — minder visuele drukte, secundaire knoppen achter één tik
- **Minimaal** — toont standaard alleen essentiële taakinformatie (pictogram, naam, duur)

In de modus Minimaal tonen tikken op een taak zowel de knoppen als alle tekstdetails van die taak.

---

### 3.5 Geavanceerd

#### Foutopsporingsmodus (snelle timers)
**Standaard:** Uit

Wanneer ingeschakeld, wordt de tijd versneld: 1 uur wordt behandeld als 1 minuut. Deze modus is uitsluitend bedoeld voor testen en ontwikkeling. Gebruik deze modus niet tijdens normaal gebruik.

---

## 4. Schemaweergave

Het schema wordt weergegeven als een verticale lijst van taken, elk voorgesteld als een gekleurde tegel.

### Taakregelindeling

Elke tegel toont:
- **Taakkleur** (linkerrand) — geeft het taaktype aan (zie [Sectie 10](#10-taaktypes))
- **Taaknaam** — bijv. "Mentale taak", "Fysieke pauze", "Lunch"
- **Tijdsbereik** — begintijd en eindtijd (bijv. 09:00 – 10:30)
- **Duur** — weergegeven in uren en/of minuten
- **Mentale batterijbereik** — het energieniveau aan het begin en einde van de taak (voor mentale taken en pauzes)

### Taakstatussen

- **Gepland** — normaal uiterlijk, volledige kleur
- **Actief (huidige taak)** — prominent weergegeven bovenaan het scherm met een grote timer
- **Voltooid** — weergegeven met doorgestreepte tekst

---

## 5. Bediening actieve taak

Wanneer een taak wordt uitgevoerd, verschijnt het huidige taakpaneel bovenaan het scherm met:

- **Taaknaam**
- **Begin- en eindtijden**
- **Afteltimer** — weergegeven in MM:SS-formaat in een groot, kleurgecodeerd blok
- **Mentale batterij-indicator** — een voortgangsbalk die je huidige energieniveau toont (zie [Sectie 7](#7-mentale-batterij))
- **Bedieningsknoppen** — Pauzeren, Stoppen en Volgende

### Pauzeren / Hervatten
Tik op **Pauzeren** om de afteltimer te pauzeren. De eindtijd van de taak wordt dienovereenkomstig aangepast. Tik op **Hervatten** om de taak voort te zetten.

Wanneer de app is gepauzeerd en naar de achtergrond is verplaatst, wordt het alarm vooraf gepland zodat het op het juiste tijdstip afgaat, ook als de app is geminimaliseerd.

### Stoppen
Tik op **Stoppen** om de huidige taak onmiddellijk te beëindigen zonder naar de volgende te gaan. Het schema blijft ongewijzigd. Gebruik dit als je de huidige taakstroom wilt verlaten zonder verder te gaan.

### Volgende
Tik op **Volgende** om de huidige taak vroegtijdig te beëindigen en naar de volgende taak te gaan. De resterende tijd van de huidige taak wordt afgerond op de dichtstbijzijnde 5 minuten en toegevoegd als een extra mentale taak aan het einde van het schema, zodat je totale werkuren toch worden gehaald.

---

## 6. Het schema aanpassen

Je kunt individuele taken in de schemalijst aanpassen terwijl de dag loopt (of voor het starten).

Om de aanpassingsbedieningselementen voor een taak zichtbaar te maken, tik je op het **bewerkingspictogram** aan de rechterkant van de taakreegel.

### Taakduur verlengen (+10 min)
Tik op **+10 min** om 10 minuten aan een taak toe te voegen. Voor mentale taken mag de duur de geconfigureerde maximale mentale taaktijd niet overschrijden. Voor rust- en fysieke pauzes kan de duur vrij worden verlengd.

### Taakduur verkorten (−10 min)
Tik op **−10 min** om een taak met 10 minuten te verkorten. De minimale duur voor elke taak is 10 minuten. Voor rust- en fysieke pauzes is de minimaal toegestane duur berekend op basis van de voorafgaande mentale taak (zie [Sectie 9](#9-planningslogica)).

### Pauzetype wisselen
Voor rust- en fysieke pauzes wisselt een wisselknop de taak tussen het type **Rust** en **Fysiek**. Dit heeft geen invloed op de duur of positie in het schema.

### Herberekening van het schema
Na elke aanpassing wordt het schema automatisch herberekend:
- **Wanneer je een taak verkort**: als de totale werkuren tekortkomen, wordt aan het einde een extra mentale taak toegevoegd om het tekort aan te vullen
- **Wanneer je een taak verlengt**: eerder automatisch gegenereerde vultaken worden verkort of verwijderd als ze niet meer nodig zijn

---

## 7. Mentale batterij

De mentale batterij vertegenwoordigt je cognitieve energieniveau gedurende de dag. Deze wordt weergegeven als een percentagebalk in het huidige taakpaneel.

### Hoe het werkt

- **Daalt** tijdens mentale taken en lunch
- **Stijgt** tijdens fysieke pauzes, rustpauzes en fietsritten
- **Bereik**: 0% (leeg) tot 100% (vol)
- De batterij begint op 100% aan het begin van de dag

### Laad- en ontlaadsnelheid

De batterij daalt en stijgt op snelheden die zijn afgeleid van je instellingen:
- **Ontlaadsnelheid** is gebaseerd op de instelling Maximale duur mentale taak: een volledige mentale taak laat de batterij dalen van het niveau aan het begin van die taak naar 0%
- **Laadsnelheid** is gebaseerd op de instelling Minimale duur fysieke taak: een minimale pauze laadt de batterij op om de ontlading van de voorafgaande taak te compenseren

### Batterijweergave

Het energiebereik van elke taak (begin % → einde %) wordt weergegeven in de schemategel. Het live actuele percentage wordt weergegeven in het actieve taakpaneel tijdens een lopende taak.

---

## 8. Meldingen

ErgoTimer gebruikt Android-meldingen om je op de hoogte te houden terwijl de app op de achtergrond werkt.

### Huidige taakmelding (permanent)
Een permanente melding wordt weergegeven in de Android-meldingsbalk terwijl een taak actief is. Deze toont:
- De naam van de huidige taak
- De resterende tijd (elke circa 30 seconden bijgewerkt)

### Taakvoltooidingsmelding
Wanneer de timer van een taak nul bereikt:
- Speelt er een alarmgeluid (indien ingeschakeld)
- Wordt er een melding weergegeven met "Taak voltooid!"
- Verschijnt er een dialoogvenster in de app (als de app op de voorgrond is)

### Micropauzemelding
Als micropauzeherinneringen zijn ingeschakeld, verschijnt er op het geconfigureerde interval een melding tijdens mentale taken, die aanmoedigt tot een korte pauze.

### Meldingskanalen
ErgoTimer gebruikt twee meldingskanalen:
- **Huidige taak** — de permanente taakvoortgangsmelding
- **Taakvoltooiingswaarschuwingen** — alarmmelding en micropauzeherinneringen

Je kunt deze kanalen afzonderlijk beheren in de systeemmeldingsinstellingen van Android voor ErgoTimer.

---

## 9. Planningslogica

### Schema genereren

Wanneer je op **Schema genereren** tikt, bouwt ErgoTimer een volledig dagschema als volgt:

1. **Optionele fietsrit (voor)** — toegevoegd op de begintijd indien geconfigureerd
2. **Mentale taken** — werkuren verdeeld in blokken, elk tot de maximale mentale taakduur
3. **Pauzes** — een fysieke of rustpauze wordt ingevoegd na elk blok mentale taken
4. **Lunch** — ingevoegd als een vast ankerpunt op de geconfigureerde lunchtijd, met 30 minuten rust erna
5. **Resterend werk** — mentale taken gaan door na de post-lunchrust
6. **Optionele fietsrit (na)** — toegevoegd aan het einde indien geconfigureerd

### Berekening van de rustduur

De minimale rusttijd na een mentale taak wordt proportioneel berekend:

```
min_rust = (duur_mentale_taak / max_mentale_duur) × min_fysieke_duur
```

Deze waarde wordt altijd naar boven afgerond op het dichtstbijzijnde veelvoud van 10 minuten.

**Voorbeeld:**  
Maximale mentale duur = 120 min, Minimale fysieke duur = 30 min, Mentale taak = 60 min  
→ min_rust = (60 / 120) × 30 = 15 min → afgerond naar boven = 20 min

### Lunch splitsen

Als een mentale taak de geconfigureerde lunchtijd zou overlappen, wordt deze automatisch gesplitst:
- Het eerste deel eindigt op de lunchtijdstijd (minimum 10 minuten)
- Lunch wordt ingevoegd op de vaste tijd
- 30 minuten rust volgen na de lunch
- Het resterende werk wordt hervat na de rust

### Bewaren van werkuren

De planner zorgt er altijd voor dat de totale mentale werktijd gelijk is aan de geconfigureerde totale werkuren:
- Wanneer een taak wordt verkort, wordt aan het einde een automatisch gegenereerde taak toegevoegd
- Wanneer een taak wordt verlengd, worden eerder automatisch gegenereerde taken verkort of verwijderd
- Wanneer op "Volgende" wordt gedrukt, wordt de ongebruikte tijd als nieuwe taak aan het einde toegevoegd (afgerond op 5 minuten)

### Harde beperkingen

- Een mentale taak zal de geconfigureerde maximale mentale taakduur nooit overschrijden
- Een rust- of fysieke pauze na een mentale taak zal nooit korter zijn dan de berekende minimum
- De lunchtijd is vast en kan niet worden overschreven
- Alle taken hebben een minimale duur van 10 minuten

---

## 10. Taaktypes

| Type | Kleur | Beschrijving |
|---|---|---|
| **Mentale taak** | 🟢 Groen | Gericht werk dat concentratie vereist. Verlaagt de mentale batterij. |
| **Fysieke pauze** | 🔴 Rood | Actieve fysieke activiteit (bijv. wandelen, fietsen). Laadt de mentale batterij op. |
| **Rustpauze** | 🔵 Blauw | Stille rust met minimale activiteit. Laadt de mentale batterij op. |
| **Lunch** | 🟣 Paars | Vaste lunchperiode. Laadt of ontlaadt de batterij niet op dezelfde manier als werk of rust. |
| **Fietsrit (voor)** | 🔴 Rood | Fietsen voor het begin van de werkdag. |
| **Fietsrit (na)** | 🔴 Rood | Fietsen na het einde van de werkdag. |
| **Rust (na lunch)** | 🔵 Blauw | Automatische rustperiode van 30 minuten na elke lunchperiode. |

---

## 11. Talen

ErgoTimer ondersteunt de volgende talen:

| Taal | Code |
|---|---|
| Engels | `en` |
| Nederlands | `nl` |

Om de taal te wijzigen, ga naar Instellingen → Interface → Taal.

---

*Voor vragen of ondersteuning, neem contact op via [ddt3@redgrendel.com](mailto:ddt3@redgrendel.com)*
