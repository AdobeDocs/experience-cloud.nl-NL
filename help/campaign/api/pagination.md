---
title: Paginering
description: Leer hoe u pagineringsbewerkingen kunt uitvoeren.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# Paginering

Standaard worden 25 bronnen in een lijst geladen.

Met de parameter **_lineCount** kunt u het aantal bronnen beperken dat in de reactie wordt vermeld.  U kunt de **volgende** knoop dan gebruiken om de volgende resultaten te tonen.

>[!NOTE]
>
>Gebruik altijd de waarde URL die in **volgende** knoop is teruggekeerd om een pagineringsverzoek uit te voeren.
>
>Het **_lineStart** verzoek wordt berekend en moet altijd binnen URL worden gebruikt die in **volgende** knoop is teruggekeerd.

<br/>

***verzoek van de Steekproef***

Voorbeeld van GET-verzoek om 1 record van de profielbron weer te geven.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Reactie op het verzoek, met **volgende** knoop om paginering uit te voeren.

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

Door gebrek, is de **volgende** knoop niet beschikbaar wanneer het in wisselwerking staan met lijsten met grote hoeveelheid gegevens. Om paginering uit te kunnen voeren, moet u de **_forcePagination=true** parameter aan uw vraag URL toevoegen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Het aantal verslagen waarboven een lijst als groot wordt beschouwd wordt bepaald in Campaign Standard **XtkBigTableThreshold** optie. De standaardwaarde is 100.000 records.
