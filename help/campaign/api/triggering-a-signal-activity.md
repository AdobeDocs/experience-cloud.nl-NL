---
title: Een signaalactiviteit activeren
description: Leer hoe u een signaalactiviteit activeert met API's.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: 9f94e98f-fe04-4369-8946-1380e02cdece
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 2%

---

# Een signaalactiviteit activeren {#triggering-a-signal-activity}

In een werkschema van Adobe Campaign Standard, kan er één of meerdere **Externe signaal** activiteiten zijn. Deze activiteiten zijn &#39;listeners&#39; die wachten om te worden geactiveerd.

Campaign Standard APIs laat u een **Externe signaal** activiteit teweegbrengen om een werkschema te roepen. De API-aanroep kan parameters bevatten die worden opgenomen in de gebeurtenisvariabelen van de workflow (een doelnaam, een bestandsnaam die moet worden geïmporteerd, een deel van de berichtinhoud, enz.). Op deze manier kunt u uw campagneautomatisering eenvoudig integreren met uw externe systeem.

>[!NOTE]
>
>Externe signaalactiviteiten kunnen niet vaker dan om de 10 minuten worden geactiveerd en dat de doelworkflow al moet worden uitgevoerd.

Volg onderstaande stappen om een workflow te activeren:

1. Voer a **GET** verzoek op het werkschema uit om de Externe trekker URL van de signaalactiviteit terug te winnen.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Voer a **POST** verzoek op teruggekeerde URL uit om de signaalactiviteit, met de **&quot;bron&quot;** parameter in de nuttige lading teweeg te brengen. Dit kenmerk is verplicht, zodat u de activerende aanvraagbron kunt aangeven.

Als u het werkschema met parameters wilt roepen, voeg hen in de nuttige lading met **&quot;parameters&quot;** attributen toe. De syntaxis bestaat uit de naam van de parameter die door zijn waarde wordt gevolgd (de volgende types worden gesteund: **koord**, **aantal**, **boolean** en **datum/tijd**).

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>Wanneer het toevoegen van een parameter aan de nuttige lading, zorg ervoor dat zijn **naam** en **type** waarden met de informatie verenigbaar zijn die in de Externe signaalactiviteit wordt verklaard. Bovendien mag de omvang van de lading niet groter zijn dan 64 Ko.

<br/>

***verzoek van de Steekproef***

Voer een GET-aanvraag uit voor de workflow.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Het retourneert de activiteit van het workflowsignaal en de bijbehorende trigger-URL.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Om een signaalactiviteit teweeg te brengen, voer een verzoek van POST op de trekkerURL met &quot;bron&quot;uit. Voeg de kenmerken &quot;parameters&quot; toe als u de workflow met parameters wilt aanroepen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Als een van de parameters niet wordt gedeclareerd in de externe signaalactiviteit, retourneert de POST-aanvraag de onderstaande fout die aangeeft welke parameter ontbreekt.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
