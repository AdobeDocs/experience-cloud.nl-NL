---
title: Profielen bijwerken
description: Meer informatie over het bijwerken van profielen met API's
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 1%

---

# Profielen bijwerken met API&#39;s{#updating-profiles-api}

Het bijwerken van profielen wordt uitgevoerd met a **PATCH** verzoek.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. De eerste stap moet **het profiel** terugwinnen.

1. In een tweede verzoek, voer het verzoek van a **PATCH** op het profiel met de voltooide informatie in de nuttige lading uit.

1. Om te controleren of het profiel door de PATCH-aanvraag is bijgewerkt, kunnen we een laatste GET-aanvraag uitvoeren.

<br/>

***verzoek van de Steekproef***

Voorbeeld van een GET-aanvraag om een profiel op te halen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Antwoord op het verzoek.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH request to update the &quot;phone&quot; attribute.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

De URL en PKEY worden geretourneerd om het bijgewerkte profiel op te halen.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
