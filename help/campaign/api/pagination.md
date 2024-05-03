---
title: Paginering
description: Leer hoe u pagineringsbewerkingen kunt uitvoeren.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# Paginering

Standaard worden 25 bronnen in een lijst geladen.

De **_lineCount** Met deze parameter kunt u het aantal bronnen beperken dat in de reactie wordt vermeld.  U kunt dan de **next** knooppunt om de volgende resultaten weer te geven.

>[!NOTE]
>
>Gebruik altijd de URL-waarde die wordt geretourneerd in het dialoogvenster **next** knooppunt om een pagineringsverzoek uit te voeren.
>
>De **_lineStart** request is berekend en moet altijd worden gebruikt binnen de URL die wordt geretourneerd in het dialoogvenster **next** knooppunt.

<br/>

***Voorbeeldverzoek***

Voorbeeld van GET-verzoek om 1 record van de profielbron weer te geven.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Antwoord op het verzoek, met de **next** knooppunt om paginering uit te voeren.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Standaard worden de **next** knooppunt is niet beschikbaar bij interactie met tabellen met een grote hoeveelheid gegevens. Als u paginering wilt kunnen uitvoeren, moet u de opdracht **_forcePagination=true** parameter aan uw vraag URL.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Het aantal records waarboven een tabel als groot wordt beschouwd, wordt in Campaign Standard gedefinieerd **XtkBigTableThreshold** -optie. De standaardwaarde is 100.000 records.
