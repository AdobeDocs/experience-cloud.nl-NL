---
title: Een service met API's maken
description: Leer hoe u een service maakt met API's
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Een service met API&#39;s maken{#creating-a-service-api}

Services maken wordt uitgevoerd met een **POST** verzoek op het de dienstmiddel.

Als u de dienst met specifieke attributen wilt tot stand brengen, voeg hen in de lading toe. Anders, zal de nieuwe dienst met standaarddegenen worden gecreeerd.

<br/>

***Voorbeeldverzoek***

De vraag van de POST van de steekproef om de dienst met specifieke attributen tot stand te brengen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

De nieuwe service wordt met de bijgewerkte kenmerken geretourneerd.

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
