---
title: Eindpunten
description: Meer informatie over de eindpunten van de API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: 14d8cf78192bcad7b89cc70827f5672bd6e07f4a
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Eindpunten {#endpoints}

De beschikbare eindpunten voor de Adobe Campaign REST API:

* **/profileAndServices**: interactie met uit de vakgebieden. Uitgebreide velden zijn niet toegankelijk met dit eindpunt.
* **/profileAndServicesExt**: communiceer met douanevelden die tijdens de uitbreiding van het Profiel of van de Dienstbron worden toegevoegd. Voor meer op douanemiddelen, verwijs naar [ deze sectie ](custom-resources.md).
* **/&lt;transactieAPI>**: interactie met de transactie berichten API (de naam van het transactie berichten API eindpunt hangt van uw instantieconfiguratie af). Raadpleeg [deze sectie](managing-transactional-messages.md) voor meer informatie.
* **/ workflow/uitvoering** : communiceer met workflows. Raadpleeg [deze sectie](controlling-a-workflow.md) voor meer informatie.

Door gebrek, zijn de belangrijkste middelen beschikbaar voor **profileAndServices** en **profileAndServicesExt** APIs:

* **/profile**: interactie met profielen van het gegevensbestand van de Campagne. Om profielen aan de dienst toe te voegen, gebruik het **/dienst** eindpunt. Voor meer op profielen in Campagne, verwijs naar de [ documentatie van de Campagne ](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: beheer abonnementsservices. Voor meer op de diensten in Campagne, verwijs naar de [ documentatie van de Campagne ](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alle andere middelen die zijn uitgebreid of gecreeerd zijn beschikbaar via **ProfileAndServicesExt** slechts API. Zij moeten met het **1&rbrace; middel van het Profiel &lbrace;worden verbonden om toegankelijk te zijn.**
