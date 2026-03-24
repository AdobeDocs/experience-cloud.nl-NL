---
title: SDK-benchmarking
description: Bekijk de resultaten van Java SDK-benchmarking voor Adobe Experience Rollouts, inclusief meetwaarden voor de responstijd voor verschillende aantallen functiemarkeringen onder normale laadvoorwaarden.
source-git-commit: 8b8b5db1a28af3a3ac29aecf26482f70eb84c714
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---


# SDK-benchmarking {#sdk-benchmarking}

De Experience Rollouts Java SDK is benchmarkd om integratieteams een betrouwbare schatting te geven van de bronnen en responstijden die worden verwacht wanneer de SDK binnen hun infrastructuur loopt.

## Testomgeving {#test-environment}

Benchmarking werd uitgevoerd op een toepassing van de Lente Boot met de volgende vaste configuratie:

* **de kernen van CPU:** 8
* **JVM geheugen:** 4096 MB

## Testhypothesen {#test-assumptions}

De volgende voorwaarden werden in alle benchmarktests constant gehouden:

* Geteste elementmarkeringen: 8 tot 128
* Contextvariabelen per functiemarkering: 2 (type `STRING`, lengte 36 tekens)
* Gemiddelde belasting: 15.000 verzoeken per minuut (rpm)
* Actieve draden: 100

## Resultaten {#results}

In de onderstaande tabel ziet u de responstijd van 99,99% voor `getFeatures()` -aanroepen terwijl het aantal functiemarkeringen toeneemt:

| Aantal functiemarkeringen | Contextvariabelen per vlag | Responstijd (ms, p99,99) |
|---|---|---|
| 8 | 2 | &lt; 0.5 |
| 16 | 2 | &lt; 0.5 |
| 32 | 2 | &lt; 0.5 |
| 64 | 2 | &lt; 1 |
| 128 | 2 | &lt; 1 |

## De resultaten interpreteren {#interpretation}

Bovenstaande benchmarks geven de prestaties weer onder de beschreven specifieke testomstandigheden. Omdat de SDK in de infrastructuur van uw toepassing wordt uitgevoerd, variëren de werkelijke responstijden afhankelijk van de specifieke factoren voor uw omgeving:

* Beschikbaar CPU en aantal kernen
* JVM-heapgrootte en afvalophalingsgedrag
* De beschikbaarheid van de draad en contextomschakeling
* Huidige systeembelasting op moment van aanvraag

Gebruik deze cijfers als planningsbasislijn eerder dan als gegarandeerde prestatiedoelen voor uw productieomgeving.

## Zie ook {#see-also}

* [Integratiehandleiding voor Java SDK](java/java-sdk-integration-guide.md)
* [Opmerkingen bij de release Java SDK](java/java-sdk-release-notes.md)
* [SDK&#39;s](../integrate/sdks.md)
