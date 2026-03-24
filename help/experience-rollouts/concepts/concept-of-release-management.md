---
title: Begrip van releasebeheer
description: Leer hoe releasebeheer in Experience Rollouts helpt bij het coördineren van grote uitrol van functies voor meerdere teams via functiemarkering.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---


# Begrip van releasebeheer {#concept-of-release-management}

De grote versies delen een paar gemeenschappelijke uitdagingen: de veelvoudige teams zijn betrokken, planningsconflict, en de gebiedsdelen zijn moeilijk te coördineren. Het beheer van de versie richt deze uitdagingen door een gestructureerde manier te verstrekken om veranderingen regelmatig uit te voeren.

## Wat betekent releasebeheer {#what-it-means}

Het beheer van de release omvat de coördinatie van een releaseeinde tot het einde — vanaf het moment dat teams zich achter functiemarkeringen beginnen te ontwikkelen tot het moment dat de functie volledig beschikbaar is voor alle gebruikers.

Hierdoor kunnen teams:

* Distribueer zelfstandig en in eigen tempo productie zonder functies voor eindgebruikers te onthullen
* Alleen live gaan wanneer alle deelnemende teams gereed zijn
* Geleidelijk de versie aan een ondergroep gebruikers vóór volledige beschikbaarheid uitvoeren

## Hoe het in de Rollouts van de Ervaring werkt {#how-it-works}

Het beheer van de versie in de Rollouts van de Ervaring bouwt op het concept [ eigenschap het flagging ](what-is-a-feature-flag.md) voort. Elk team stelt hun code aan productie achter een eigenschapvlag op. Een versie is dan a **inzameling van eigenschapvlaggen die over veelvoudige toepassingen en teams** worden bepaald.

Wanneer alle teams klaar zijn, kan de versie in één enkele verrichting worden geactiveerd — of geleidelijk worden ingevoerd — zonder om het even welk individueel team dat plaatsingstijdstip moet hergroeperen of coördineren.

Deze aanpak voorziet in:

* **Onafhankelijke plaatsing** — De teams stellen op hun eigen programma op zonder andere teams of eindgebruikers te beïnvloeden.
* **gecoördineerde activering** — Alle vlaggen in een versie worden samen geactiveerd wanneer de versie levend gaat.
* **Graduele rollout** - de versie kan geleidelijk aan stijgende percentages van gebruikers worden geopend.

Voor details bij het vormen van versies in de Rollouts van de Ervaring, zie [ beheer van de Versie ](release-management.md).
