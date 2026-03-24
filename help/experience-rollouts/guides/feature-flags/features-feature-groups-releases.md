---
title: Functies, functiegroepen en releases
description: Leer over de verschillen tussen eigenschapmarkeringen, eigenschapgroepen, dwars-team eigenschapgroepen, en versies in de Rollouts van de Ervaring van Adobe en wanneer om elk te gebruiken.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---


# Functies, functiegroepen en releases {#features-feature-groups-releases}

Rollouts van de ervaring verstrekt vier artefacten voor het beheren van eigenschaprollouts. De keuze van de juiste is afhankelijk van het bereik van de rollout, het aantal betrokken teams en het doelpubliek voor de benodigde mogelijkheden.

## De vier artefacten {#artifacts}

**markering van de Eigenschap**
De meest atoomeenheid. Beheert één functie voor één toepassing, die eigendom is van één team. Kan voor een bepaald publiek worden in- of uitgeschakeld.

**de groep van de Eigenschap**
Een verzameling functievlaggen die bij hetzelfde team horen. Hiermee kunt u meerdere vlaggen in meerdere toepassingen in één team als één eenheid beheren.

**van de de eigenschapgroep van 0} dwars-team
Breidt mogelijkheden van de eigenschapgroep over veelvoudige teams en toepassingen uit.** Zelf-bedient en steunt rijke publiekscriteria, maar steunt geen caching.

**Versie**
Ontworpen voor grote, gecoördineerde rollouts over veelvoudige teams en toepassingen. Gebruikt authentificatie op token-gebaseerde publiek richten. Ondersteunt caching op de server-SDK.

## Vergelijking {#comparison}

| | Functiemarkering | Functiegroep | Groep met functies voor meerdere teams | Geen |
|---|---|---|---|---|
| **Rol die wordt vereist om publiek** te beheren | Eigenaar van productrelease | Eigenaar van productrelease | Functiebeheerder | Release Manager |
| **Toepassingen** | Enkel | Meerdere (zelfde team) | Meerdere (meerdere teams) | Meerdere (meerdere teams) |
| **Teams** | Enkel | Enkel | Cross-team | Cross-team |
| **Rijke publiekscriteria** | ✓ | ✓ | ✓ | Beperkt |
| **de uitrol van het Percentage** | Gecombineerd met alle publiekscriteria | Gecombineerd met alle publiekscriteria | Gecombineerd met alle publiekscriteria | Gecombineerd met vaste publiekscriteria |
| **het testen A/B** | ✓ | ✓ | ✗ | ✗ |
| **Caching in server SDK** | Alleen markeringen voor in- en uitschakelen | Geen caching | Geen caching | Alle releases worden lokaal in cache geplaatst |
| **Zelf-dient** | ✓ | ✓ | ✓ | Vereist supportverzoek |
| **spoor van de Controle** | ✓ | ✓ | ✓ | ✓ |

## Wanneer gebruikt u elk {#when-to-use}

| Scenario | Gebruiken |
|---|---|
| Eén functie voor één toepassing testen of implementeren | **markering van de Eigenschap** |
| Meerdere functies in hetzelfde team coördineren en tegelijk actief worden | **de groep van de Eigenschap** |
| Het coördineren van eigenschappen over toepassingen in verschillende teams, met rijke het richten | **van de de eigenschapgroep van 0} dwars-team** |
| Grote gecoördineerde release voor meerdere teams, met caching op SDK-niveau | **Versie** |

## Zie ook {#see-also}

* [De eerste functiemarkering maken](create-your-first-feature-flag.md)
* [Een functiegroep maken](create-a-feature-group.md)
* [Een functiegroep voor meerdere teams maken](create-cross-team-feature-group.md)
* [Versies en groepen met meerdere functies](releases-and-cross-team-feature-groups.md)
