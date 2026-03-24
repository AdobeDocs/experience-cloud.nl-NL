---
title: Opmerkingen bij de release Node.js SDK
description: Release-aantekeningen voor de Experience Rollouts Node.js SDK, inclusief een wijziging van nieuwe functies, verbeteringen en foutoplossingen in alle gepubliceerde versies.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---


# Opmerkingen bij de release Node.js SDK {#nodejs-sdk-release-notes}

Deze pagina bevat de releasegeschiedenis van de Experience Rollouts Node.js SDK. Voor integratieopstelling, zie [ Node.js de integratiegids van SDK ](nodejs-sdk-integration-guide.md).

## Versie 1.0.10 {#v1-0-10}

**fixes van de insect en contactdoosverbeteringen**

* Correctie `ESOCKETTIMEDOUT` van uitzondering die werd gegenereerd tijdens geplande cachefouten. De parameter `maxSockets` is verwijderd uit `featureRequestHttpParams` en `ingestAnalyticsHttpParams` in `createInstance()` .
* Het probleem waarbij cacheable clients onjuist werden gemarkeerd als niet-cacheable na HTTP 304 (Niet gewijzigd)-reacties, is opgelost.
* Verwijderd `isReleaseBitEnabled()` — deze methode wordt niet meer ondersteund.
* Verbeterde logboekuitvoer voor betere diagnostiek.
* Test- en dekkingsmappen worden niet meer opgenomen in het gepubliceerde npm-pakket.

## Versie 1.0.5 {#v1-0-5}

**de verbeteringen van de Stabiliteit**

Algemene oplossingen voor de verwerking van vernieuwingen in cache en SDK-initialisatiefouten.

## Versie 1.0.3 {#v1-0-3}

**Aanvankelijke stabiele versie**

Eerste productievrijgave van SDK Node.js die voor authentiek verklaarde, anonieme, en standaard volledig-uitzettingseigenschapmarkeringen herwinnen steunt.

## Zie ook {#see-also}

* [Node.js SDK Integration guide](nodejs-sdk-integration-guide.md)
* [Opmerkingen bij de release Java SDK](../../sdk-releases/java/java-sdk-release-notes.md)
* [SDK&#39;s](../../integrate/sdks.md)
