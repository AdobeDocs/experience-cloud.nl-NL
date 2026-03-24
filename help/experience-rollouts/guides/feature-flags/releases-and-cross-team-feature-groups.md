---
title: Versies en groepen met meerdere functies
description: Leer het verschil tussen versies en multiteam eigenschapgroepen in de Rollouts van de Ervaring van Adobe en wanneer om elk voor gecoördineerde multiteam rollouts te gebruiken.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Versies en groepen met meerdere functies {#releases-and-cross-team}

Zowel steunen de versies als de dwars-teameigenschapgroepen gecoördineerde rollouts over veelvoudige teams en toepassingen. De juiste keuze is afhankelijk van uw cachevereisten, doelgerichtheid van het publiek en de mate waarin u controle over het proces wilt hebben.

## Groepen met functies voor verschillende teams {#cross-team-feature-groups}

Een multiteam eigenschapgroep staat u toe om eigenschapmarkeringen van toepassingen te bundelen die door verschillende teams worden bezeten en hen met rijke publiekscriteria te leiden.

Belangrijkste kenmerken:

* **Zelf-server** — Geen steunverzoek wordt vereist om tot één te leiden
* **Rich publiek richtend** — Steunt de volledige reeks publiekscriteria (profielattributen, contextvariabelen, percentageruitrol)
* **Geen grens** op het aantal u kunt creëren
* **geen caching** — De de vlagevaluaties van de Eigenschap vereisen een API vraag; SDK-Vlakke caching wordt niet gesteund

Voor geleidelijke verwezenlijking instructies, zie [&#x200B; tot een dwars-teameigenschapgroep &#x200B;](create-cross-team-feature-group.md) leiden.

## Uitstoot {#releases}

Een release is ontworpen voor grote, gecoördineerde lanceringen waar caching op SDK-niveau vereist is. De versies gebruiken authentificatie op teken-gebaseerde publiek het richten.

Belangrijkste kenmerken:

* **vereist een steunverzoek** — De versies zijn niet volledig zelf-dienen; de steun van Rollouts van de Ervaring van het contact om tot één te leiden
* **SDK caching** — Al versiegegevens worden in het voorgeheugen ondergebracht plaatselijk in de serverSDK, die API vraag vermindert
* **Beperkte publiekscriteria** — de regels van het publiek zijn gebaseerd op authentificatietokens (land, e-mail, gebruiker - identiteitskaart, percentage, enz.)
* **Beperkte actieve versies** — Een eindig aantal actieve versies kan in een tijd bestaan; van plan om versies binnen drie maanden te sluiten of te basislijn

## Vergelijking {#comparison}

| | Groep met functies voor meerdere teams | Geen |
|---|---|---|
| Zelf | ✓ | Vereist supportverzoek |
| Rijke publiekscriteria | ✓ | Beperkt |
| A/B-tests | ✗ | ✗ |
| SDK caching | ✗ | ✓ |
| Actieve limiet | Geen limiet | Beperkt |

## Aanbeveling {#recommendation}

Als uw gebruiksgeval rijk publiek het richten en zelf-dient beheer impliceert, gebruik a **dwars-teameigenschapgroep**. Als uw backenddiensten SDK-Vlakke caching vereisen en de eenvoudigere publiekscriteria van versies voldoende zijn, gebruik a **versie**.

## Zie ook {#see-also}

* [Functies, functiegroepen en releases](features-feature-groups-releases.md)
* [Een functiegroep voor meerdere teams maken](create-cross-team-feature-group.md)
* [Release aanvragen](request-a-release.md)
