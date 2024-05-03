---
title: Aangepaste bronnen
description: Meer informatie over het beheer van aangepaste bronnen met API's/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 2%

---

# Aangepaste bronnen {#custom-resources}

Adobe Campaign wordt geleverd met een vooraf gedefinieerd gegevensmodel, waarbij gegevens via verschillende bronnen worden gedefinieerd. U kunt het gegevensmodel verrijken dat wordt verstrekt door de middelen uit te breiden om uw eigen douanevelden of douanetabellen, zoals aankoop of productlijsten toe te voegen.

Aangepaste bronnen zijn toegankelijk via API&#39;s die de **/profileAndServicesExt** en de naam van de aangepaste bron.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Voor middelen die niet uit-van-de-doos zijn, gebruik altijd <b>&quot;cus&quot;</b> voor de naam van de bron.

U kunt elke gewenste bewerking uitvoeren met aangepaste bronnen, mits deze zijn gekoppeld aan de tabel Profiel. Neem bijvoorbeeld de onderstaande tabelstructuur:

![alt-tekst](assets/cusresources.png)

In dat geval alle middelen van het **Transactie**, **TransactieDetails** en **Product** tabellen zijn beschikbaar zolang ze gekoppeld zijn aan de **Profiel** tabel.

<br/>

***Voorbeeldverzoek***

Het verzoek van de GET van de steekproef om tot het uitgebreide profileAndServicesExt middel toegang te hebben.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Het keert de lijst van alle verbonden douanemiddelen terug. Vervolgens kunt u de bron-URL&#39;s gebruiken om elke API-taak uit te voeren die in deze documentatie wordt beschreven.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```
