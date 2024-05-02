---
title: Sorteren
description: Meer informatie over het uitvoeren van sorteerbewerkingen
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Sorteren

Sorteren is standaard in oplopende volgorde beschikbaar. Als u in aflopende volgorde wilt sorteren, voegt u **%20desc** aan de **_order** waarde van de parameter.

Als u wilt weten of een veld kan worden gesorteerd, controleert u de parameter &quot;sortable&quot; in de metagegevens van de bron. Raadpleeg [deze sectie](metadata-mechanism.md) voor meer informatie.

<br/>

***Voorbeeldverzoeken***

* Voorbeeld van een GET-aanvraag om e-mailberichten op te halen in de database in alfabetische volgorde.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Antwoord op het verzoek.

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* Voorbeeld van een GET-aanvraag om de e-mail in de database op te halen in aflopende alfavolgorde.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Antwoord op het verzoek.

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```
