---
title: SDK's
description: Meer informatie over de SDK-architectuur in Adobe Experience Rollouts en de beschikbare SDK's voor Java en Node.js.
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: 2a946868f58e25f8aafbf3ccfcf6571e7d0d8d20
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# SDK&#39;s {#sdks}

De Rollouts van de ervaring verstrekt server-kant SDKs voor achterste de dienstintegratie. Op deze pagina vindt u een beschrijving van de SDK-architectuur en de beschikbare opties.

## SDK-architectuur {#architecture}

Alle Experience Rollouts SDK&#39;s hebben dezelfde kernarchitectuur:

* **Initialisatie** — SDK wordt gevormd via a `createInstance()` vraag die een singleton voorwerp terugkeert.
* **herwinning van de Eigenschap** - de `getFeatures()` methode wint eigenschapvlaggegevens van SDK terug.
* **Caching** — SDK caches reacties van de dienst van Rollouts van de Ervaring. Een Manager van het Geheime voorgeheugen verfrist het geheime voorgeheugen op een configureerbaar opiniepeilingsinterval (TTL).
* **Fout die** behandelt - als de dienst 503 terugkeert, behoudt de Manager van het Geheime voorgeheugen de bestaande caching gegevens en gaat het dienen van eigenschapvlagevaluaties verder. Als de gegevens niet sinds de laatste vraag (304) zijn veranderd, wordt het geheime voorgeheugen niet bijgewerkt.

## Vereisten {#prerequisites}

Voordat u een SDK gaat integreren, moet u het volgende doen:

1. **identiteitskaart van de Toepassing** — Cliënt identiteitskaart voor elke toepassing die in de console van Rollouts van de Ervaring wordt ingezien.
2. **het teken van de Dienst** — Gebruikt door SDK om de Rollouts APIs van de Ervaring op de achtergrond te roepen.
3. **API sleutel** — Gebruikt naast het de dienstteken voor API authentificatie.

## Beschikbare SDK&#39;s {#available-sdks}

### Java SDK {#java-sdk}

De Java SDK wordt via Maven gedistribueerd. Voeg de afhankelijkheid van uw project `pom.xml` toe om te integreren. Voor toepassingen op basis van vering stelt de Geweven afhankelijkheid automatisch de SDK-cache in voordat uw toepassing volledig wordt geladen.

Belangrijke specificaties voor de Java SDK:

* **Ondersteunde JDK:** JDK 8 en later
* **niet-cacheable cliënten:** gesteund van versie 0.8 van SDK verder. Voor niet-cachebare clients wordt door `getFeature()` een live API-aanroep uitgevoerd in plaats van te lezen vanuit cache. De SDK gaat verder met de opiniepeiling op de achtergrond en schakelt over naar cache-gebaseerde serving als de client cacheable wordt.

Zie de [&#x200B; de integratiegids van SDK van Java &#x200B;](../sdk-releases/java/java-sdk-integration-guide.md) voor opstellingsinstructies.

### Node.js SDK {#nodejs-sdk}

De Node.js SDK wordt gedistribueerd via npm.

Zie [&#x200B; Node.js de integratiegids van SDK &#x200B;](../sdk-releases/nodejs/nodejs-sdk-integration-guide.md) voor opstellingsinstructies.

## Zie ook {#see-also}

* [Webservices](web-services.md)
* [Integratiestappen](integration-steps.md)
* [Integratiehandleiding voor Java SDK](../sdk-releases/java/java-sdk-integration-guide.md)
* [Node.js SDK Integration guide](../sdk-releases/nodejs/nodejs-sdk-integration-guide.md)
