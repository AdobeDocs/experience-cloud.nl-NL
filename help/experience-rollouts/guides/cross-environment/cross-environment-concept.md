---
title: Concept tussen milieu en milieu
description: Leer hoe u met de mogelijkheden voor verschillende omgevingen in Adobe Experience Rollouts toepassingen in verschillende omgevingen kunt koppelen en functiemarkeringen consistent kunt beheren, van ontwikkeling tot productie.
source-git-commit: 5c99061a7f2aaaad98190166ea6fd79b7eb26dec
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Concept tussen milieu en milieu {#cross-environment-concept}

Met de mogelijkheden voor verschillende omgevingen kunt u toepassingsinstanties in verschillende implementatieomgevingen (zoals QA, Stage en Production) met elkaar verbinden en functiemarkeringen consistent beheren vanuit Experience Rollouts.

## Het probleem wordt opgelost door de omgeving heen {#problem}

Zonder cross-environment-linking is elke toepassingsinstantie in Experience Rollouts volledig onafhankelijk van zijn tegenhangers in andere omgevingen. Hierdoor ontstaan verschillende wrijvingspunten:

* Een toepassing met de naam `my-app` in het werkgebied heeft geen relatie met `my-app` in Production. Deze toepassingen worden behandeld als afzonderlijke, niet-verwante toepassingen.
* U kunt de status van een functiemarkering niet weergeven in het werkgebied terwijl u werkt in Productie. U moet manueel van milieu&#39;s veranderen om vlagstaten te vergelijken.
* Voor het importeren van een configuratie met een functiemarkering van een lagere omgeving naar een hogere omgeving is handmatige recreatie vereist.

## Wat cross-environment toelaat {#what-it-enables}

Door toepassingsinstanties over milieu&#39;s te verbinden, kan uw team:

* Definieer welke implementatieomgevingen van uw toepassing zijn toegewezen aan welke Experience Rollouts-omgevingen
* Gebruik aangepaste omgevingslabels (bijvoorbeeld `Dev` , `Staging` , `Prod` ) die overeenkomen met de naamgevingsconventies van uw team
* De status van een functiemarkering voor alle gekoppelde omgevingen vanuit één weergave bekijken
* U kunt functiemarkeringen importeren van een lagere omgeving naar een hogere omgeving met een paar klikken, zonder ze handmatig opnieuw te maken

## Hoe omgevingen zijn gestructureerd {#environment-structure}

De Rollouts van de ervaring heeft twee platformmilieu&#39;s: **Stadium** en **Productie**. Uw toepassing kan echter meer omgevingen hebben, zoals QA, Staging en Production. Door middel van cross-environment linking kunt u bepalen waar elke omgeving van uw toepassing zich bevindt:

* De milieu&#39;s van QA en van het Staging kunnen in of het Stadium van de Rollouts van de Ervaring of het milieu van de Productie worden ontvangen.
* Productieomgevingen moeten worden gehost in de Experience Rollouts Production-omgeving.

Deze flexibiliteit betekent dat u niet gedwongen bent om naar één maateenheid toe te wijzen.

## Volgende stappen {#next-steps}

* [&#x200B; associeerde milieu&#39;s aan een toepassing &#x200B;](associate-environments.md) — opstelling het verband tussen uw toepassingsinstanties
* [&#x200B; de eigenschapvlaggen van de Mening over milieu&#39;s &#x200B;](view-feature-flags-across-environments.md) — de status van de monitorvlag over alle verbonden milieu&#39;s
* [&#x200B; de eigenschapvlaggen van de Invoer &#x200B;](import-feature-flags.md) — promoot eigenschapmarkeringen van lagere aan hogere milieu&#39;s
