---
title: Opmerkingen bij de release Java SDK
description: Opmerkingen bij de release voor de Experience Rollouts Java SDK, waaronder het wijzigen van nieuwe functies, verbeteringen en foutoplossingen in alle gepubliceerde versies.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---


# Opmerkingen bij de release Java SDK {#java-sdk-release-notes}

Deze pagina bevat de releasegeschiedenis van de Experience Rollouts Java SDK. Voor integratieopstelling, zie [ de integratiegids van SDK van Java ](java-sdk-integration-guide.md).

## Versie 4.0.6 {#v4-0-6}

**de groepsgegevens van de Controle in reacties**

U kunt nu de varianten- en besturingsgroepsgegevens ophalen in de SDK-respons, overeenkomstig het gedrag van de REST-API&#39;s. Voeg `.includeControlGroup()` toe aan de `FloodgateConfiguration` builder om dit in te schakelen.

## Versie 4.0.5 {#v4-0-5}

**de Verbeteringen van de Stabiliteit en van de prestaties**

Kleinere interne verbeteringen om de betrouwbaarheid en verbindingsverwerking van de cachevernieuwingen te vernieuwen.

## Versie 4.0.4 {#v4-0-4}

**probeer beleidsverbeteringen** opnieuw

Verbeterd standaardgedrag voor opnieuw proberen bij transient service-fouten.

## Versie 4.0.3 {#v4-0-3}

**Bugfixes**

Algemene stabiliteitscorrecties voor randgevallen bij asynchrone initialisatie.

## Versie 4.0.1 (Beta) {#v4-0-1-beta}

**Beta versie van 4.x SDK**

Introductie van ondersteuning voor DX-clients, DX-gebiedconfiguratie en AEP (sandbox).

## Versie 3.1.0 {#v3-1-0}

**Streaming steun voor cliënten DX**

Toegevoegde SSE-gebaseerde streamingmogelijkheid om SDK-clients in bijna real-time op de hoogte te stellen van vlagupdates.

## Versie 3.0.x {#v3-0-x}

**Java 11 geïntroduceerde vereiste**

Vanaf versie 3.0.0 vereist de SDK JDK 11 of hoger. Eerdere versies ondersteunen JDK 8+.

Introduceerde publiek-door-verwijzing steun voor cliënten DX, die herbruikbare publieksdefinities toestaan om door identiteitskaart in eigenschapentiteiten worden van verwijzingen voorzien.

## Versie 2.x {#v2-x}

**niet-cacheable cliëntsteun (van 0.8)**

Niet-cachebare clients kunnen `getFeature()` live aanroepen in plaats van te lezen vanuit de SDK-cache. De SDK gaat verder met de opiniepeiling op de achtergrond en schakelt over naar cache-gebaseerde serving wanneer de client cacheable wordt.

De extra verbeteringen 2.x omvatten nieuwe bouweropties (`alwaysCache()`, `neverCache()`, de cliënt van douaneHTTP en de uitvoeringspartner steun), eigenschap en versie zeer belangrijk filtreren, en imiteerde gebruikersherwinning.

## Versie 1.x {#v1-x}

Eerste releasereeks. Ondersteunde JDK 8+, Geweven gebiedsintegratie, en basis voor authentiek verklaarde en anonieme herwinning van de eigenschapmarkering.

## Zie ook {#see-also}

* [Integratiehandleiding voor Java SDK](java-sdk-integration-guide.md)
* [Opmerkingen bij de release Node.js SDK](../../sdk-releases/nodejs/nodejs-sdk-release-notes.md)
* [SDK&#39;s](../../integrate/sdks.md)
