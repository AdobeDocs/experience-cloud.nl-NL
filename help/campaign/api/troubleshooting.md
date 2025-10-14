---
title: API-probleemoplossing
description: Meer informatie over algemene problemen met API's voor Campaigns Standard
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 84b72258789ba61016deb813e93bdca0ea142712
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---

# API-problemen {#troubleshooting}

* **wanneer het gaan naar de Console Adobe.io krijgt u de volgende fout: &quot;De console van de Adobe I/O is slechts beschikbaar om leden van ondernemingsrekeningen te selecteren. Als u gelooft u toegang zou moeten hebben, gelieve uw Beheerder van het Systeem te contacteren.&quot;**

U kunt alleen API-sleutels maken voor de organisaties waarvan u de beheerder bent. Als dit bericht wordt weergegeven en u API-sleutels wilt maken, vraagt u een van de beheerders van de organisatie.

* **wanneer het doen van een verzoek aan Adobe.io krijgt u {&quot;error_code&quot;:&quot;403023&quot;, &quot;bericht&quot;:&quot;Het profiel is ongeldig&quot;}**

Dit betekent dat er een probleem is met de IMS-provisioning van uw specifieke campagneproduct: het IMS-team moet dit probleem oplossen.

Als u meer details wilt, kunt u de IMS API met uw token aanroepen om te zien hoe uw IMS-profiel eruitziet: u moet een prodCtx hebben waarbij de organisatie_id dezelfde is als de id die u in uw URL voor Adobe.io plaatst om uw aanvraag te kunnen doorsturen.
Als de IMS-voorziening ontbreekt, moet deze worden hersteld.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De volgende fout wordt geretourneerd.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Controleer uw IMS-profiel met deze aanvraag.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

In de reactie, moet de waarde ORGANIZATION_ID het zelfde in uw eerste verzoek van de GET zijn.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **wanneer het doen van een verzoek aan Adobe.io krijgt u {&quot;code&quot;:500, &quot;bericht&quot;:&quot;Oeps. Er is iets misgegaan. Controleer uw URI en probeer opnieuw.&quot;}**

Adobe.io declareert uw ongeldige URI: de URI die u aanvraagt, is naar alle waarschijnlijkheid ongeldig. Op Adobe.io wanneer u de dienst van de Campagne selecteert, krijgt u een plukker met een lijst van mogelijke organisatie_ids. U moet controleren dat u kiest u in uw URL plaatst.

* **wanneer het doen van een verzoek aan Adobe.io krijgt u {&quot;error_code&quot;:&quot;401013&quot;, &quot;bericht&quot;:&quot;Het oautetoken is niet geldig&quot;}**

Uw token is ongeldig (onjuiste IMS-aanroep die wordt gebruikt om een token te genereren) of uw token is verlopen.

* **ik zie mijn profiel na verwezenlijking niet**

Afhankelijk van de instantieconfiguratie, moet het gecreeerde profiel aan een **orgUnit** worden geassocieerd. Om te begrijpen hoe te om dit gebied in uw verwezenlijking toe te voegen, raadpleeg [&#x200B; deze sectie &#x200B;](creating-profiles-api.md).

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu'un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
