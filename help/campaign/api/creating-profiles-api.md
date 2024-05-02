---
title: Profielen maken met API's
description: Meer informatie over het maken van profielen met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Profielen maken met API&#39;s {#creating-profiles-api}

Profielen maken wordt uitgevoerd met een **POST** verzoek om de profielbron.

>[!CAUTION]
>
>Als u een <b>orgUnit</b> naar het gemaakte profiel, moet u de profielbron met dit gebied uitbreiden en, na de publicatie van de uitbreiding, een verzoek van de POST op uitvoeren <b>ProfileAndServicesExt</b> eindpunt.
>
>Voor meer informatie over de het middeluitbreiding van het profiel, verwijs naar <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campagnedocumentatie</a>.

<br/>

***Voorbeeldverzoek***

Voorbeeld van POST-aanvraag om een profiel te maken met de e-mail &quot;john.doe@mail.com&quot;.

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
