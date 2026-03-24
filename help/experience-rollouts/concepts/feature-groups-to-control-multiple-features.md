---
title: Functiegroepen om meerdere functies te beheren
description: Leer hoe u met functiegroepen in Experience Rollouts gerelateerde functiemarkeringen als één eenheid in toepassingen kunt bundelen en beheren.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---


# Functiegroepen om meerdere functies te beheren {#feature-groups}

A [&#x200B; eigenschapvlag &#x200B;](what-is-a-feature-flag.md) controleert één enkele eigenschap. Wanneer u veelvoudige verwante eigenschapvlaggen samen moet beheren — en ervoor zorgt zij het zelfde publiek bereiken — gebruikt u a **eigenschapgroep**.

## Wat een functiegroep doet {#what-it-does}

Een functiegroep bundelt meerdere functiemarkeringen en biedt u de mogelijkheid één publieksregel tegelijk op alle markeringen toe te passen. Dit is nuttig wanneer één enkele gebruiker-onder ogen ziende capaciteit veelvoudige toepassingen of de diensten overspant.

Neem bijvoorbeeld een samenwerkingsfunctie waarbij u wijzigingen aanbrengt in een bureaubladtoepassing, een mobiele app en een back-endservice. Door een functiegroep te maken met vlaggen van alle drie toepassingen, kunt u de functie openen voor 1% van de gebruikers — en ervoor zorgen dat deze gebruikers een consistente ervaring op alle drie de oppervlakken tegelijk zien.

## Groepering tussen toepassingen {#cross-application}

De groepen van de eigenschap steunen het dwars-toepassingseigenschapbeheer zolang de vlaggen tot het **zelfde team** in de Rollouts van de Ervaring behoren. Één team kan veelvoudige toepassingen bezitten, zodat de verwante vlaggen over die toepassingen kunnen worden gegroepeerd.

## Functiegroepen versus releases {#vs-releases}

| | Functiegroep | Geen |
|---|---|---|
| Bereik | Binnen één team | Over meerdere teams |
| Hoofdletters gebruiken | Vlaggen in uw team coördineren | Grote, multi-team lanceringscoördinatie |
| Vereiste rechten | Teamniveau | Hoger (releasebeheer) |

Als de eigenschapvlaggen u tot toepassingen wilt groeperen die door verschillende teams worden bezeten, gebruik a [&#x200B; versie &#x200B;](release-management.md) in plaats van een eigenschapgroep.
