---
title: Profielen ophalen
description: Meer informatie over het ophalen van profielen met API's
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---

# Profielen ophalen met API&#39;s {#retrieving-profiles}

Het ophalen van profielen wordt uitgevoerd met een **GET** verzoek.

Vervolgens kunt u de zoekopdracht verfijnen door filters, volgorde en paginering te gebruiken. Raadpleeg voor meer informatie de [Aanvullende bewerkingen](sorting.md) sectie.

Bovendien kunt u met Campaign Standard-API&#39;s zoeken naar profielen op basis van een van deze velden: e-mail, voornaam, achternaam of een aangepast veld. Raadpleeg [deze sectie](#searching-field) voor meer informatie.

<br/>

***Voorbeeldverzoeken***

* Voorbeeld van GET-aanvraag om alle profielen op te halen.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
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
              "firstName": "John",
              "lastName":"Doe",
              "birthDate": "1980-10-24",
              ...
          },
          ...
  }
  ```

* Voorbeeld van een GET-aanvraag om de eerste 10 e-mailwaarden op te halen.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Antwoord op het verzoek. Het knooppunt &quot;next&quot; retourneert de URL die u toegang biedt tot de tien volgende e-mailwaarden.

  ```
  {
  "content": [
      "amy.dakota@mail.com",
      "kristen.smith@mail.com",
      "omalley@mail.com",
      "xander.harrys@mail.com",
      "jane.summer@mail.com",
      "gloria.boston@mail.com",
      "edward.snow@mail.com",
      "dorian.simons@mail.com",
      "peter.paolini@mail.com",
      "mingam+test08@adobe.com"
  ],
  "next": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
      lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
  }
  }
  ```

## Zoeken naar profielen op basis van een veld {#searching-field}

De **[!UICONTROL filterType]** kunt u profielen ophalen op basis van een van de volgende velden: e-mail, voornaam, achternaam of elk aangepast veld dat is toegevoegd bij Geavanceerd filteren tijdens het uitbreiden van de profielbron.

>[!NOTE]
>
>Zoekopdrachten zijn hoofdlettergevoelig en worden alleen op voorvoegsels uitgevoerd. U kunt bijvoorbeeld niet zoeken naar een profiel met de laatste letters van de achternaam.

***Voorbeeldverzoeken***

* Voorbeeldverzoek om profielen te filteren op basis van voornaam.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Voorbeeldverzoek om profielen te filteren op basis van achternaam.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Voorbeeldverzoek om profielen te filteren op basis van e-mail.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Voorbeeldverzoek om profielen te filteren op basis van het aangepaste veld &quot;Hobby&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```
