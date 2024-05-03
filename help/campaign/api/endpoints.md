---
title: Eindpunten
description: Meer informatie over de eindpunten van de API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Eindpunten {#endpoints}

De beschikbare eindpunten voor de Adobe Campaign REST API:

* **/profileAndServices**: communiceer met velden buiten het vak. Uitgebreide velden zijn niet toegankelijk met dit eindpunt.
* **/profileAndServicesExt**: communiceer met douanevelden die tijdens de uitbreiding van het Middel van het Profiel of van de Diensten worden toegevoegd. Raadpleeg voor meer informatie over aangepaste bronnen [deze sectie](custom-resources.md).
* **/&lt;transactionalapi>**: communiceer met de transactie berichten API (de naam van het transactie berichten API eindpunt hangt van uw instantieconfiguratie af). Raadpleeg [deze sectie](managing-transactional-messages.md) voor meer informatie.
* **/workflow/uitvoering**: communiceer met workflows. Raadpleeg [deze sectie](controlling-a-workflow.md) voor meer informatie.

Standaard zijn de belangrijkste bronnen beschikbaar voor de **profileAndServices** en **profileAndServicesExt** API&#39;s zijn:

* **/profile**: communiceer met profielen uit de Campagne-database. Als u profielen wilt toevoegen aan een service, gebruikt u de opdracht **/service** eindpunt. Voor meer informatie over profielen in Campagne, verwijs naar [Campagnedocumentatie](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: abonnementsservices beheren. Raadpleeg voor meer informatie over services in Campagne de [Campagnedocumentatie](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alle andere bronnen die zijn uitgebreid of gemaakt, zijn beschikbaar via de **ProfileAndServicesExt** Alleen API. Zij moeten gekoppeld zijn aan de **Profiel** om toegankelijk te zijn.
