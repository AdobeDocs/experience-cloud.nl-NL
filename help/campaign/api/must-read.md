---
title: Lees hier meer
description: Moet worden gelezen voordat API's kunnen worden gebruikt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# Doorzichtig {#must-read}

## Technische voorschriften

* Adobe Campaign API&#39;s mogen alleen worden gebruikt op Server.
* Neem altijd contact op met de technische contactpersoon van de Adobe als het gebruiksscenario dat u wilt implementeren is uitgelijnd met de schaal die is toegestaan door Adobe Campaign API&#39;s.
* Voor het instellen van een AdobeIO-toegang zijn specifieke machtigingen vereist. Neem contact op met de Adobe Support voor problemen.

## Rechten en toegang

* Adobe Campaign API&#39;s gebruiken standaard de beheerderscontext en dus zijn de eenheden en rollen van de organisatie niet van toepassing.
* De Adobe Campaign API&#39;s zijn uitgesloten van de rolcontext.
* Als u APIs met een organisatieeenheid of een rollen wilt vormen, gelieve eerst met uw aan Adobe technische contact te controleren.

## Bronrepresentatie

Alle API-bronnen zijn beschikbaar in **JSON** met een URL-extensie of in een HTTP Accept Header:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Zonder extensie in de URL **de json-indeling is de standaardindeling** voor het inhoudstype.

<br/>

***aanvraagvoorbeeld***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Primaire sleutel en URL&#39;s

* Probeer niet zelf een URL te maken. Alle URL&#39;s worden geretourneerd door de API. Het is echter mogelijk een URL te maken op basis van de resourcenaam op het hoogste niveau.

* De waarden voor de automatische primaire sleutel (PKey) die de voorbeelden illustreren, zijn niet bedoeld om in een andere specifieke implementatie te werken. Ze worden gemaakt door de Adobe Campaign API.

* Door Adobe Campaign gegenereerde waarden voor Automatische primaire sleutels mogen nooit worden opgeslagen in een externe database of website. U moet specifieke zeer belangrijke gebieden in uw gegevensbestanddefinitie produceren en het gebruiken tijdens uw ontwikkelingen.

## Aangepaste toetsen {#custom-keys}

Als de profielbron is uitgebreid met een veld met een aangepaste sleutel, kunt u dit veld gebruiken als een sleutel in plaats van de automatische primaire sleutel die door Adobe Campaign wordt gegenereerd:

`GET /.../profileAndServicesExt/profile/<customKey>`

Aangepaste toetsen kunnen niet worden gewijzigd met een PATCH-bewerking als de sleutelwaarde afwijkt van de oorspronkelijke sleutel of als u uw eigen zakelijke sleutel gebruikt als URI in plaats van de sleutel die door de Adobe wordt verschaft.

Een aangepaste sleutel gebruiken voor **profielbronnen op hoofdniveau** alleen. URL&#39;s worden geretourneerd door de API en mogen nooit door uzelf worden gemaakt.

<br/>

***Voorbeeldverzoek***

Als u de abonnementen voor een profiel wilt ophalen met behulp van een aangepaste sleutel, voert u een GET-bewerking uit op de aangepaste sleutel.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Voer een GET-aanvraag uit op de geretourneerde abonnements-URL.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De lijst met abonnementen voor het profiel wordt geretourneerd.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
