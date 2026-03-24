---
title: Modus Experience Rolouts
description: Leer over de twee eigenschap richtend wijzen in de Rollouts van de Ervaring van Adobe — gebruiker-vlakke gericht en org-niveau gericht - en wanneer om elk te gebruiken.
source-git-commit: bb4541dd7a77edadded2edbc9c71905cf70f2e24
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# Modus Experience Rolouts {#modes}

De Rollouts van de ervaring verstrekt twee verschillende eigenschap richtingswijzen. Elk programma heeft een ander doel voor het beheer van de release en is ontworpen voor een specifiek type toepassing of gebruiksgeval.

>[!TIP]
>
>Kies de modus op basis van wat u beheert: afzonderlijke gebruikerssessies of organisatie en omgevingsbereik.

## Doelstelling op gebruikersniveau {#user-level}

### Overzicht {#user-level-overview}

Het doel op gebruikersniveau laat eigenschapuitrol op het individuele gebruikersniveau toe. Het steunt nauwkeurige het richten van specifieke gebruikers, interne meetapparaten, kanariële gebruikers, en op percentage-gebaseerde geleidelijke rollouts.

Deze modus is het meest geschikt voor toepassingen die de ervaring moeten variëren op basis van wie is aangemeld.

### Wanneer gebruiken {#user-level-when}

Gebruik een gebruikergericht doel wanneer u wilt:

* Een functie inschakelen voor specifieke gebruikers
* A/B-experimenten uitvoeren
* Kanariële tests uitvoeren met een kleine groep voor een bredere implementatie
* Een functie geleidelijk implementeren op percentage van gebruikers
* De ervaring nauwkeurig afstellen op basis van individuele gebruikerskenmerken (zoals gegevens uit het e-maildomein of het profiel)

### Beperkingen {#user-level-limitations}

Het doel op gebruikersniveau wordt niet ontworpen voor de volgende scenario&#39;s:

* Beheert geen functies op organisatie-, omgeving- of regioniveau
* Niet bedoeld voor functie-activering voor gehele huurder of functie-indeling

## Doelstelling op het niveau van organisatie en milieu {#org-level}

### Overzicht {#org-level-overview}

Het richten op het niveau van de organisatie laat eigenschapuitrol bij de organisatie, het milieu, en gebiedswerkingsgebied toe. Het controleert eigenschapbeschikbaarheid over volledige organisaties of specifieke plaatsingsmilieu&#39;s, eerder dan voor individuele gebruikers.

Deze modus is ontworpen voor functionaliteit op bedrijfsniveau en omgevingspecifieke rollouts.

### Wanneer gebruiken {#org-level-when}

Gebruik gericht op org-niveau wanneer u wilt:

* Een functie inschakelen voor een hele organisatie
* Beschikbaarheid van besturingsfuncties via omgeving (bijvoorbeeld werkgebied versus productie)
* Een regionale uitrol uitvoeren
* Gatefuncties op basis van machtiging of abonnementniveau

### Beperkingen {#org-level-limitations}

Het richten van de orde en milieu-niveau wordt niet ontworpen voor de volgende scenario&#39;s:

* Biedt geen ondersteuning voor doelgerichte gebruikers met gebruikersprofielen
* Biedt geen ondersteuning voor op percentages gebaseerde rollout op individueel gebruikersniveau
* Niet bedoeld voor experimenten of A/B-tests

## Vergelijking {#comparison}

| Dimension | Doelstelling op gebruikersniveau | Doelstelling op het niveau van organisatie en milieu |
|---|---|---|
| Bereik van controle | Individuele gebruiker | Organisatie, milieu, regio |
| Doelbasis | Gebruikersprofiel en -kenmerken | Org- en omgevingscontext |
| Percentage uitrol | Ja | Nee |
| A/B-tests | Ja | Nee |
| Enterprise-gaming | Nee | Ja |

## De rechtermodus kiezen {#choosing}

* Als uw vraag *&quot;is welke gebruikers deze eigenschap zouden moeten zien?&quot;* → Gebruik **gebruiker-vlakke het richten**
* Als uw vraag *&quot;is welke organisaties of milieu&#39;s deze eigenschap zouden moeten hebben?&quot;* → Het gebruik **org en milieu-niveau richtend**
