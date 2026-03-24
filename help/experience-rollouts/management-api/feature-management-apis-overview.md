---
title: Overzicht van API's voor functiebeheer
description: Overzicht van het beheer APIs van Rollouts van de Ervaring, die u toestaan om eigenschapmarkeringen, eigenschapgroepen, en versies programmatically tot stand te brengen, te lezen bij te werken en te schrappen.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---


# Overzicht van API&#39;s voor functiebeheer {#feature-management-apis-overview}

Met de API&#39;s voor het beheer van Experience Rollouts kunt u functiemarkeringen, functiegroepen en -releases programmatisch beheren. Teams die workflows moeten automatiseren of Experience Rollouts moeten integreren in bestaande implementatiepijplijnen, kunnen deze API&#39;s gebruiken in plaats van de console.

>[!NOTE]
>
>Toegang tot beheer APIs die een de dienstteken gebruiken wordt verleend op verzoek. De steun van Rollouts van de Ervaring van het contact en verstrekt een bedrijfsrechtvaardiging om toegang te verzoeken.

## Beschikbare beheer-API&#39;s {#available-apis}

De volgende beheer-API&#39;s zijn beschikbaar:

* [&#x200B; de vlaggen van de Eigenschap beheer API &#x200B;](feature-flags-management-api.md) - creeer, lees, werk, en schrap eigenschapvlaggen voor een toepassing bij.
* [&#x200B; het groepsbeheer API van de Eigenschap &#x200B;](feature-group-management-api.md) - creeer, leest, werk, schrapt, en controle geautomatiseerde uitrolplannen voor eigenschapgroepen.
* [&#x200B; beheer APIs van de Versie &#x200B;](release-management-apis.md) - creeer en geef de groepen en versies van de dwars-teameigenschap uit.

## Algemene eisen {#common-requirements}

Voor alle API-aanroepen voor beheer is het volgende vereist:

* Een **API sleutel** van Adobe Developer Console - zie [&#x200B; aan de API toepassing &#x200B;](../guides/integrate/subscribe-to-api-application.md) intekenen.
* Een **IMS toegangstoken van de gebruikerstoegang** of **de dienstteken**, die als `Bearer <token>` in de `Authorization` kopbal wordt overgegaan.
* A `Content-Type: application/json` header.

API-sleutels en tokens moeten afzonderlijk worden ingericht voor werkgebied- en productieomgevingen.

## Helphulplijnen {#helper-guides}

De volgende hulplijnen helpen u bij het maken van correcte API-ladingen:

* [&#x200B; krijgt cliëntidentiteitskaart voor een toepassing &#x200B;](get-client-id.md) - bekijk omhoog numerieke cliëntidentiteitskaart die door de eigenschapvlaggen en het beheer APIs van de eigenschapgroep wordt vereist.
* [&#x200B; krijgt gewenste publiekscriteria &#x200B;](get-audience-criteria.md) - gebruik de console en GET API om de correcte publiekscriteria JSON structuur te produceren.
* [&#x200B; het flardAPI van het Beheer &#x200B;](management-patch-api.md) — Werk individuele gebieden van een eigenschapvlag, eigenschapgroep, of dwars-teameigenschapgroep bij zonder het volledige voorwerp over te gaan.

## Zie ook {#see-also}

* [GET Feature API V3](../feature-api/get-feature-api-v3.md)
* [GET Feature API V2](../feature-api/get-feature-api-v2.md)
* [Abonneren op de API-toepassing](../guides/integrate/subscribe-to-api-application.md)
