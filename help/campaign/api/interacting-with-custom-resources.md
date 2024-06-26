---
title: Interactie met aangepaste bronnen
description: Meer informatie over het beheer van aangepaste bronnen met API's/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Interactie met aangepaste bronnen {#interacting-with-custom-resources}

De **/customResources** het eindpunt staat u toe om de de douanemiddelen van de Campagne in REST bloot te stellen. Op basis van deze API is er een integratie tussen aangepaste entiteiten en externe eindpunten beschikbaar.

Het /customResources eindpunt heeft precies het zelfde gedrag zoals /profileAndServices eindpunt.

De aangepaste bronnen die worden weergegeven in deze API zijn:

* alle entiteiten die niet onder /profileAndServicesExt worden blootgesteld
* alle entiteiten die niet aan een profiel zijn gekoppeld en, voor deze entiteiten, hun kinderen en kleinkinderen.
* standaard alle entiteiten die niet aan iets zijn gekoppeld, en hun kinderen en kleinkinderen.

>[!NOTE]
>De douanemiddelen die onder /profileAndServicesExt beschikbaar zijn worden niet blootgesteld in /customResources API.


Hier volgt een voorbeeld om de metagegevens op te halen uit een aangepaste bron:

```
GET /customResources/resourceType/<customResourceName>
```

Voor het maken, bijwerken of verwijderen worden de GET, POST, PATCH, DELETE gebruikt.

```
POST /customResources/<customResourceName>
```
