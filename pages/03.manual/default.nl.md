---
title: Handleiding
---

## ErgoTimer — Handleiding

## Inhoudsopgave

1. [Overzicht](#1-overzicht)
2. [Hoofdscherm](#2-hoofdscherm)
3. [Instellingen](#3-instellingen)
   - 3.0 [Mijn dag](#30-mijn-dag)
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

Zodra een schema is gegenereerd, toont het scherm de volledige dag als een scrollbare kalendertijdlijn. Onderaan verschijnen actieknoppen:
- **Taak toevoegen** — voeg handmatig een taak toe aan je schema
- **Nu Inhaken** — spring in op het huidige punt van het bestaande schema op basis van de huidige tijd
- **Nu starten** — genereert het volledige schema opnieuw met de huidige tijd als begin van het werkvenster en start onmiddellijk de eerste taak. Alleen beschikbaar binnen 60 minuten na de geconfigureerde begintijd van het werkvenster.

---

## 3. Instellingen

Open de instellingen door op het pictogram **⚙️** rechtsboven in het hoofdscherm te tikken. Instellingen zijn georganiseerd in inklapbare secties. Tik op een sectieheader om deze in of uit te klappen. Tik op **Schema genereren** onderaan om je instellingen toe te passen en een nieuw schema aan te maken.

### 3.0 Mijn dag

Deze sectie bepaalt de grenzen van je volledige dag. De planner gebruikt deze tijden om te beslissen waar taken mogen worden geplaatst.

#### Wektijd
De tijd waarop je opstaat. Er worden nooit taken vóór dit tijdstip geplaatst.

#### Bedtijd
De tijd waarop je dag eindigt. Taken worden nooit verder uitgesteld dan dit tijdstip.

#### Begin werkvenster
De vroegste tijd waarop de planner mentaal werk mag plaatsen. Dit is het begin van je actieve werkperiode.

#### Einde werkvenster
De uiterste tijd waarop werk mag eindigen. Geen gegenereerde mentale taak loopt voorbij deze grens.

---

### 3.1 Basisschema

#### Totaal werkuren
**Bereik:** 1 uur tot 9 uur, in stappen van 0,5 uur  
**Standaard:** 4 uur

Het totale aantal uren mentaal werk dat in de dag wordt ingepland. Fysieke pauzes, rustmomenten en vaste ankers tellen niet mee — alleen mentale taken.

#### Maximale duur mentale taak
**Bereik:** 30 minuten tot 180 minuten (3 uur), in stappen van 30 minuten  
**Standaard:** 120 minuten (2 uur)

De maximale aaneengesloten duur van één mentale taak. Wanneer een mentale taak deze limiet bereikt, zal de planner altijd een pauze invoegen voor verdere mentale arbeid wordt toegestaan. Dit is een harde limiet — geen enkele mentale taak in het gegenereerde schema zal deze waarde overschrijden.

#### Minimale duur fysieke taak
**Bereik:** 5 minuten tot 60 minuten, in stappen van 5 minuten  
**Standaard:** 15 minuten

De minimale lengte van een fysieke of rustpauze ingevoegd tussen mentale taken. Dit wordt gebruikt als basiswaarde — de werkelijke pauzelengtes worden berekend met de verhouding beschreven in [Sectie 9](#9-planningslogica).

#### Begintijd
De tijd waarop je werkdag begint. Stel het uur en de minuut in met de tijdkiezer. De planner gebruikt dit als begin van de eerste vrije periode die met gegenereerd werk kan worden gevuld.

---

### 3.2 Pauzes & herstel

#### Vaste ankers

Vaste ankers zijn niet-verplaatsbare blokken in het schema voor lunch, vergaderingen, afspraken, therapie, reistijd of geplande hersteltijd. Elk anker heeft:

- **Naam** — wordt direct in het schema getoond
- **Ankertype** — bepaalt wanneer het anker in het schema wordt geplaatst
- **Energie-effect** — hoe het anker de mentale batterij beïnvloedt

Ankertypes:

- **Vaste tijd** — geplaatst op een specifiek begin- en eindtijdstip, die direct worden ingesteld. In de ankerlijst worden de begin- en eindtijd weergegeven.
- **Voor werk** — geplaatst direct voor de start van het werkvenster, met een instelbare duur. In de ankerlijst worden het ankertype en de duur weergegeven in plaats van een tijdsbereik.
- **Na werk** — geplaatst direct na afloop van het laatste gegenereerde werktaak, met een instelbare duur. Ankers met vaste tijden die later op de dag gepland staan, worden hier niet door beïnvloed. In de ankerlijst worden het ankertype en de duur weergegeven in plaats van een tijdsbereik.

Energie-effecten:

- **Uitputtend** — werkt voor de batterij als mentale arbeid
- **Neutraal** — reserveert tijd zonder de batterij te veranderen
- **Herstellend** — werkt voor de batterij als een herstellende pauze

De planner plaatst nooit automatisch werk binnen een vast anker. In plaats daarvan vult hij de vrije periodes voor, tussen en na de ankers.

In de instellingen gebruikt elke ankerkaart een compacte lay-out met twee rijen: de eerste rij toont het ankerpictogram, de naam en metadata; de tweede rij bevat de schakelaar en de knoppen voor bewerken/verwijderen.

Gedrag bij overlap van ankers met vaste tijden:

- Je kunt overlappende ankers met vaste tijden opslaan.
- Als overlappende ankers met vaste tijden allebei **ingeschakeld** zijn, worden die ankerkaarten in de instellingen met een rode rand gemarkeerd.
- Het genereren van een schema wordt geblokkeerd wanneer ingeschakelde ankers met vaste tijden overlappen. Schakel een van de conflicterende ankers uit en genereer opnieuw.

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
- **Standaard** — taakblokken tonen taaknaam, duur en het energiebereik per taak (begin % → einde %). In de header van de actieve taak blijft de live batterij-percentagebalk zichtbaar.
- **Rustig** — taakblokken tonen taaknaam en duur met zachtere visuele styling; het energiebereik per taak wordt in blokken verborgen. In de header van de actieve taak blijft de live batterij-percentagebalk zichtbaar.
- **Minimaal** — taakblokken zijn alleen iconen en in de header van de actieve taak wordt de batterij-percentagebalk verborgen.

---

### 3.5 Geavanceerd

#### Foutopsporingsmodus (snelle timers)
**Standaard:** Uit

Wanneer ingeschakeld, wordt de tijd versneld: 1 uur wordt behandeld als 1 minuut. Deze modus is uitsluitend bedoeld voor testen en ontwikkeling. Gebruik deze modus niet tijdens normaal gebruik.

---

## 4. Schemaweergave

Het schema wordt weergegeven als een scrollbare verticale tijdlijn (kalenderweergave). Een tijdas aan de linkerkant toont kloktijden; kleurgecodeerde taakblokken worden op hun exacte positie op de as geplaatst. Een horizontale "nu"-lijn beweegt door de tijdlijn naarmate de tijd verstrijkt, zodat je altijd in één oogopslag kunt zien waar je in je dag staat.

Als er een lege tussenruimte bestaat tussen twee geplande taken, toont ErgoTimer op die plaats een subtiele aanklikbare tussenregel. Door op de tussenruimte te tikken open je het dialoogvenster Taak toevoegen, vooraf ingevuld met de volledige begin- en eindtijd van die vrije periode.

### Taakblokindeling

Elk blok toont:
- **Kleur** — geeft het taaktype aan (zie [Sectie 10](#10-taaktypes))
- **Taaknaam** — bijv. "Mentale taak", "Fysieke pauze" of de naam van je vaste anker
- **Tijdsbereik** — begintijd en eindtijd
- **Duur** — weergegeven in uren en/of minuten
- **Mentale batterijbereik** — het energieniveau aan het begin en einde van de taak

De kleuren van taakblokken blijven gekoppeld aan het taaktype, maar de blokvulling is verzacht voor betere leesbaarheid en minder visuele intensiteit.

Door op elk taakblok te tikken, inclusief de huidige actieve taak, open je het detailvenster van die taak.

Korte taken (minder dan 20 minuten) gebruiken een compacte opmaak op één regel om overloop te voorkomen.

### Taakstatussen

- **Gepland** — normaal uiterlijk, volledige kleur
- **Actief (huidige taak)** — pulseert zacht om de aandacht te trekken; weergegeven met afteltimer
- **Voltooid** — weergegeven met verminderde transparantie

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

Je kunt individuele taken in het schema aanpassen terwijl de dag loopt (of voor het starten).

Tik op een taakblok om het detailvenster met beschikbare acties te openen.

### Een taak toevoegen in een lege tussenruimte
Als er zichtbare vrije tijd tussen twee taken staat, tik je op de tussenregel om het tijdsgebonden dialoogvenster Taak toevoegen te openen. Het dialoogvenster is vooraf ingevuld met de volledige grenzen van die tussenruimte. Daarna geeft ErgoTimer de taak direct door aan de planner, die indien nodig zelf een veiligheidsrust invoegt of een grote mentale taak opsplitst in meerdere mentale blokken en pauzes.

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

- **Daalt** tijdens mentale taken en uitputtende vaste ankers
- **Stijgt** tijdens fysieke pauzes, rustpauzes en herstellende vaste ankers
- **Blijft gelijk** tijdens neutrale vaste ankers
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
- Een live afteltimer — geïmplementeerd met Android's ingebouwde chronometer, zodat de weergegeven tijd continu en correct wordt bijgewerkt, ook wanneer de app op de achtergrond staat, zonder dat de app actief hoeft te zijn.

### Taakvoltooidingsmelding
Wanneer de timer van een taak nul bereikt:
- Speelt er een alarmgeluid (indien ingeschakeld)
- Wordt er een melding weergegeven met "Taak voltooid!"
- Verschijnt er een dialoogvenster in de app (als de app op de voorgrond is)

Taakvoltooiingsalarmen worden gepland via Android's wekker-mechanisme (`AlarmManager.setAlarmClock()`). Dit zorgt ervoor dat het alarm op exact het geplande tijdstip afgaat, zelfs als het apparaat in energiebesparingsmodus of Doze-modus staat. Een klein wekker-pictogram (⏰) verschijnt in de Android-statusbalk zolang er een alarm gepland staat.

### Melding volgende taak (rustige periode)
Wanneer een taak voltooid is maar de volgende taak pas later gepland staat, gaat ErgoTimer in een rustige tussenpauze en keert terug naar het schemaoverzicht zonder actieve taak. Er wordt alvast een achtergrondwekker gepland voor de starttijd van de volgende taak. Wanneer dat moment aanbreekt:
- Als de app op de voorgrond is, start de taak automatisch
- Als de app op de achtergrond is, wordt er een melding weergegeven om je te laten weten dat je volgende geplande taak op het punt staat te beginnen

### Micropauzemelding
Als micropauzeherinneringen zijn ingeschakeld, verschijnt er op het geconfigureerde interval een melding tijdens mentale taken, die aanmoedigt tot een korte pauze. Net als taakvoltooiingsalarmen maken micropauzeherinneringen gebruik van het wekker-mechanisme voor betrouwbare bezorging.

### Meldingskanalen
ErgoTimer gebruikt twee meldingskanalen:
- **Huidige taak** — de permanente taakvoortgangsmelding
- **Taakvoltooiingswaarschuwingen** — alarmmelding en micropauzeherinneringen

Je kunt deze kanalen afzonderlijk beheren in de systeemmeldingsinstellingen van Android voor ErgoTimer.

---

## 9. Planningslogica

### Schema genereren

Wanneer je op **Schema genereren** tikt, bouwt ErgoTimer een volledig dagschema als volgt:

1. **Vaste ankers** worden op starttijd gesorteerd
2. **Mentale taken** worden gegenereerd in de beschikbare vrije periodes, elk tot de maximale mentale taakduur
3. **Pauzes** worden ingevoegd tussen mentale blokken wanneer dat nodig is
4. **Vaste-tijdankers** worden ongewijzigd ingevoegd op hun geconfigureerde tijden
5. **Resterend werk** gaat door in latere vrije periodes tot het totale werkdoel is bereikt
6. **Na-werk-ankers** worden direct na het laatste gegenereerde werktaak geplaatst, ongeacht eventuele vaste-tijdankers die later op de dag gepland staan

### Berekening van de rustduur

De minimale rusttijd na een mentale taak wordt proportioneel berekend:

```
min_rust = (duur_mentale_taak / max_mentale_duur) × min_fysieke_duur
```

Deze waarde wordt altijd naar boven afgerond op het dichtstbijzijnde veelvoud van 10 minuten.

**Voorbeeld:**  
Maximale mentale duur = 120 min, Minimale fysieke duur = 30 min, Mentale taak = 60 min  
→ min_rust = (60 / 120) × 30 = 15 min → afgerond naar boven = 20 min

### Ankerbewust plannen

Als een gegenereerd mentaal blok een vast anker zou overlappen, stopt de planner met vullen van die vrije periode en voegt hij het anker op exact de geconfigureerde tijd in. Mentaal werk wordt pas hervat in de volgende vrije periode, en het energie-effect van het anker wordt toegepast op basis van de duur ervan.

### Bewaren van werkuren

De planner zorgt er altijd voor dat de totale mentale werktijd gelijk is aan de geconfigureerde totale werkuren:
- Wanneer een taak wordt verkort, wordt aan het einde een automatisch gegenereerde taak toegevoegd
- Wanneer een taak wordt verlengd, worden eerder automatisch gegenereerde taken verkort of verwijderd
- Wanneer op "Volgende" wordt gedrukt, wordt de ongebruikte tijd als nieuwe taak aan het einde toegevoegd (afgerond op 5 minuten)

### Harde beperkingen

- Een mentale taak zal de geconfigureerde maximale mentale taakduur nooit overschrijden
- Een rust- of fysieke pauze na een mentale taak zal nooit korter zijn dan de berekende minimum
- De tijden van vaste ankers zijn vast en kunnen niet worden overschreven
- Alle taken hebben een minimale duur van 10 minuten

---

## 10. Taaktypes

| Type | Kleur | Beschrijving |
|---|---|---|
| **Mentale taak** | 🟢 Groen | Gericht werk dat concentratie vereist. Verlaagt de mentale batterij. |
| **Fysieke pauze** | 🔴 Rood | Actieve fysieke activiteit (bijv. wandelen, fietsen). Laadt de mentale batterij op. |
| **Rustpauze** | 🔵 Blauw | Stille rust met minimale activiteit. Laadt de mentale batterij op. |
| **Vast anker (uitputtend)** | 🟢 Groen | Een vast blok dat energie kost zoals mentale arbeid, bijvoorbeeld een vergadering. |
| **Vast anker (neutraal)** | ⚪ Grijs | Een vast blok dat tijd reserveert zonder energieverandering, bijvoorbeeld lunch of reistijd. |
| **Vast anker (herstellend)** | 🔵 Blauw | Een vast blok dat energie herstelt zoals een pauze, bijvoorbeeld therapie of geplande rust. |

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

<div class="right-align">
ErgoTimer versie 0.2.0
</div>
