---
title: Profielen maken met API's
description: Meer informatie over het maken van profielen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Profielen maken met API&#39;s {#creating-profiles-api}

Het creëren van profielen wordt uitgevoerd met a **POST** verzoek op het profielmiddel.

>[!CAUTION]
>
>Als u een <b> orgUnit </b> aan het gecreeerde profiel wilt associëren, moet u het profielmiddel met dit gebied uitbreiden en, na de publicatie van de uitbreiding, een verzoek van de POST op het <b> ProfileAndServicesExt </b> eindpunt uitvoeren.
>
>Voor meer op de het middeluitbreiding van het profiel, verwijs naar de <a href="https://helpx.adobe.com/nl/campaign/standard/administration/using/organizational-units.html#partitioning-profiles"> documentatie van de Campagne </a>.

<br/>

***verzoek van de Steekproef***

Voorbeeld van een POST-aanvraag om een profiel te maken met de e-mail &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Het nieuwe profiel wordt geretourneerd met het e-mailadres &quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
