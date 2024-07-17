---
title: Transactionele berichten beheren
description: Leer hoe u transactieberichten beheert met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
hidefromtoc: true
hide: true
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: 14d8cf78192bcad7b89cc70827f5672bd6e07f4a
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 1%

---

# Transactionele berichten beheren {#managing-transactional-messages}

Nadat u een transactiegebeurtenis hebt gemaakt en gepubliceerd, moet u het activeren van deze gebeurtenis integreren in uw website.

U wilt bijvoorbeeld dat de gebeurtenis &#39;Afkappen met winkelwagentje&#39; wordt geactiveerd wanneer een van uw klanten uw website verlaat voordat ze de producten in hun winkelwagentje kopen. Om dit te doen, als Webontwikkelaar, moet u de REST Transactionele Berichten API gebruiken.

1. Verzend een verzoek volgens de methode van de POST, die het [ verzenden van de transactionele gebeurtenis ](#sending-a-transactional-event) teweegbrengt.
1. Het antwoord op het verzoek van de POST bevat een Primaire Sleutel, die u toestaat om één of veelvoudige verzoeken door een verzoek van de GET te verzenden. U kunt dan de [ gebeurtenisstatus ](#transactional-event-status) verkrijgen.

## Een transactiegebeurtenis verzenden {#sending-a-transactional-event}

De transactionele gebeurtenis wordt verzonden door een verzoek van de POST met de volgende structuur URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZATION>**: uw persoonlijke ORGANIZATION ID. Zie [deze sectie](must-read.md).

* **&lt;transactieAPI>**: de Transactionele eindpunten van Berichten API.

  De naam van het Transactionele eindpunt van Berichten API hangt van uw instantieconfiguratie af. Deze komt overeen met de waarde &quot;mc&quot; gevolgd door uw persoonlijke organisatie-id. Laten we het voorbeeld van het Geometrixx-bedrijf nemen, met &#39;geometrixx&#39; als organisatie-id. In dat geval zou het verzoek om POST als volgt zijn:

  `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

  Het eindpunt van de API voor transactionele berichten is ook zichtbaar tijdens de API-voorvertoning.

* **&lt;eventID>**: het type van gebeurtenis u wilt verzenden. Deze id wordt gegenereerd wanneer de gebeurtenisconfiguratie wordt gemaakt

### POST request header

Het verzoek moet een header &quot;Content-Type: application/json&quot; bevatten.

U moet een charset, bijvoorbeeld **utf-8** toevoegen. Deze waarde is afhankelijk van de REST-toepassing die u gebruikt.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### POST aanvraaginstantie

De gebeurtenisgegevens bevinden zich in de hoofdtekst van de JSON-POST. De gebeurtenisstructuur is afhankelijk van de definitie ervan. De API voorproefknoop in het scherm van de middeldefinitie verstrekt een verzoeksteekproef.

De volgende optionele parameters kunnen aan de inhoud van de gebeurtenis worden toegevoegd om het verzenden van aan de gebeurtenis gekoppelde transactieberichten te beheren:

* **vervaldatum** (facultatief): na deze datum, zal het verzenden van de transactionele gebeurtenis worden geannuleerd.
* **gepland** (facultatief): van deze datum, zal de transactionele gebeurtenis worden verwerkt en het transactiebericht zal worden verzonden.

>[!NOTE]
>
>De waarden van de parameters &quot;expiration&quot; en &quot;scheduled&quot; volgen de ISO 8601-indeling. ISO 8601 specificeert het gebruik van de hoofdletter &quot;T&quot; om de datum en de tijd van elkaar te scheiden. Deze kan echter wel uit de invoer of uitvoer worden verwijderd voor een betere leesbaarheid.

### Antwoord op de POST

De reactie van de POST keert de status van de transactionele gebeurtenis op het tijdstip terug het werd gecreeerd. Om zijn huidige status (gebeurtenisgegevens, gebeurtenisstatus...) terug te winnen, gebruik de Primaire Sleutel door de reactie van de POST in een verzoek van de GET wordt teruggekeerd:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***verzoek van de Steekproef***

POST vraagt om de gebeurtenis te verzenden.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Antwoord op de POST verzoek.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Status van een transactiegebeurtenis {#transactional-event-status}

In het antwoord kunt u met het veld status weten of de gebeurtenis is verwerkt:

* **hangend**: de gebeurtenis is in behandeling - de gebeurtenis neemt deze status over wanneer het enkel is teweeggebracht.
* **verwerking**: de gebeurtenis wacht levering - het wordt omgezet in een bericht en het bericht wordt verzonden.
* **gepauzeerd**: het gebeurtenisproces wordt gepauzeerd. Het wordt niet meer verwerkt, maar in een rij in het gegevensbestand van Adobe Campaign bewaard.
* **verwerkt**: de gebeurtenis werd verwerkt en het bericht werd met succes verzonden.
* **genegeerd**: de gebeurtenis werd genegeerd door de levering, typisch wanneer een adres in quarantaine is.
* **deliveryFailed**: een leveringsfout voorkwam terwijl de gebeurtenis werd verwerkt.
* **routingFailed**: de verpletterende ontbroken fase - dit kan bijvoorbeeld voorkomen wanneer het type van gespecificeerde gebeurtenis niet kan worden gevonden.
* **toOld**: de gebeurtenis verliep alvorens het kon worden verwerkt - dit kan om diverse redenen gebeuren, bijvoorbeeld, wanneer verzenden verscheidene tijden ontbreekt (dit resulteert in de gebeurtenis die niet meer bijgewerkt is) of wanneer de server niet meer gebeurtenissen na het worden overbelast kan verwerken.
* **targetingFailed**: Campaign Standard slaagde er niet in om een verbinding te verrijken die voor bericht het richten wordt gebruikt.
