---
title: Functies en functiegroepen
description: Leer meer over de verschillen tussen functiemarkeringen en functiegroepen in Adobe Experience Rollouts en wanneer u ze moet gebruiken.
source-git-commit: c654ca1507abcefcff84cef9f99830042939805d
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Functies en functiegroepen {#features-feature-groups}

Rollouts van de ervaring verstrekt twee artefacten voor het beheren van eigenschaprollouts. De keuze van de juiste is afhankelijk van het bereik van de rollout en het aantal functies dat u gebruikt.

## De twee artefacten {#artifacts}

**markering van de Eigenschap**
De meest atoomeenheid. Controls a single feature for a single application. Kan voor een bepaald publiek worden in- of uitgeschakeld.

**de groep van de Eigenschap**
Een verzameling functievlaggen die bij hetzelfde team horen. Hiermee kunt u meerdere vlaggen in meerdere toepassingen als één eenheid beheren.

## Vergelijking {#comparison}

| | Functiemarkering | Functiegroep |
|---|---|---|
| **Rol die wordt vereist om publiek** te beheren | Eigenaar van productrelease | Eigenaar van productrelease |
| **Toepassingen** | Enkel | Meerdere (zelfde team) |
| **Rijke publiekscriteria** | ✓ | ✓ |
| **de uitrol van het Percentage** | Gecombineerd met alle publiekscriteria | Gecombineerd met alle publiekscriteria |
| **het testen A/B** | ✓ | ✓ |
| **Zelf-dient** | ✓ | ✓ |
| **spoor van de Controle** | ✓ | ✓ |

## Wanneer gebruikt u elk {#when-to-use}

| Scenario | Gebruiken |
|---|---|
| Eén functie voor één toepassing testen of implementeren | **markering van de Eigenschap** |
| Meerdere functies in hetzelfde team coördineren en tegelijk actief worden | **de groep van de Eigenschap** |

## Zie ook {#see-also}

* [De eerste functiemarkering maken](create-your-first-feature-flag.md)
* [Een functiegroep maken](create-a-feature-group.md)
