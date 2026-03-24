---
title: Inleiding tot Experience Rollouts
description: Leer hoe Adobe Experience Rollouts een gecontroleerd releasesysteem biedt voor het geleidelijk implementeren van functies voor doelgroepen.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# Inleiding tot Experience Rollouts {#introduction}

Adobe Experience Rollouts is een beheerd releasesysteem waarmee teams functies tot aan de productie kunnen implementeren terwijl ze exact bepalen wie ze ziet en wanneer. Een functie kan in productie zijn en onzichtbaar voor eindgebruikers — en vervolgens geleidelijk worden ingeschakeld voor een doelgroep — zonder dat er een nieuwe implementatie nodig is.

## Van ontwikkeling tot productie {#dev-to-prod}

De Rollouts van de ervaring steunt de volledige reis van een eigenschap van zijn vroegste ontwikkelingsfase tot algemene beschikbaarheid:

1. **het testen van de Ontwikkelaar** - een ontwikkelaar leidt tot een eigenschapvlag, stelt hun code aan om het even welk milieu op, en tests tegen slechts hun eigen zitting. Dit heeft geen invloed op andere gebruikers en vertakking is niet vereist.

2. **Gerichte voorproef** — Een producteigenaar verbindt een publiek aan de eigenschapvlag, die de eigenschap ter beschikking stelt van een bepaalde ondergroep van gebruikers (bijvoorbeeld, bètadeelnemers of een specifiek gebied) voor bevestiging en terugkoppelt.

3. **geleidelijke uitrol** — De eigenschap wordt progressief geopend aan een breder publiek — 1%, 10%, 50%, 100% — met de capaciteit om, de eigenschap bij om het even welke stap te pauzeren aan te passen of uit te zetten.

4. **Algemene beschikbaarheid** - Zodra de bevestiging volledig is, wordt de eigenschap ter beschikking gesteld aan alle gebruikers.

## Kernmogelijkheden {#capabilities}

De Rollouts van de ervaring is een platform van het eigenschapbeheer dat verstrekt:

* {de vlaggen van de Eigenschap 0} **— Zet om het even welke eigenschap aan of weg bij runtime voor een gericht publiek, zonder code opnieuw op te stellen.**

* **publiek richtend** — Controle die een eigenschap ziet gebruikend gegevens van het gebruikersprofiel, op percentage-gebaseerde regels, e-mailadres, e-maildomein, IP adres, of contextafhankelijke attributen.

* **de groepen van de Eigenschap** — Bundel veelvoudige verwante eigenschapmarkeringen over toepassingen en beheer hen als één enkele eenheid, die het zelfde publiek verzekeren ziet een verenigbare ervaring.

* **Versies** — Coördineer grote, dwars-teamrollouts door eigenschapvlaggen van veelvoudige teams en toepassingen in één enkele versiegebeurtenis te groeperen.

* **Graduele rollouts** — De eigenschaplevering van de Fase incrementeel om risico te verminderen, verzamelt terugkoppelt, en leidt backendlading.

* **Kill schakelaar** - draai van om het even welke eigenschap onmiddellijk als een probleem wordt ontdekt, zonder een codeverandering of herplaatsing.
