---
title: Node.js SDK Integration guide
description: Leer hoe u de Experience Rollouts Node.js SDK kunt integreren in uw back-endservice om functiemarkeringen op te halen en te evalueren.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# Node.js SDK Integration guide {#nodejs-sdk-integration-guide}

The Experience Rollouts Node.js SDK is a server-side library intended for Node.js services. Het plaatst de gegevens van de eigenschapvlag plaatselijk in het voorgeheugen en evalueert vlaggen zonder een synchrone API vraag op elk verzoek.

>[!NOTE]
>
>De SDK Node.js is alleen ontworpen voor gebruik op de server. Roep voor client-side webtoepassingen het kenmerkAPI V3 REST-eindpunt rechtstreeks aan.

## Vereisten {#prerequisites}

Voordat u de SDK Node.js gaat integreren, moet u controleren of u beschikt over:

* Een Node.js-servertoepassing
* Een **API sleutel** en **de dienstteken** dat door Adobe Developer Console wordt verkregen — zie [&#x200B; aan de API toepassing &#x200B;](../../integrate/subscribe-to-api-application.md) intekenen
* Uw **toepassings cliënt IDs** die in de console van Rollouts van de Ervaring wordt geregistreerd — zie [&#x200B; Onboard uw toepassing &#x200B;](../../applications/onboard-your-application.md)

## De SDK installeren {#install}

Voeg de SDK toe aan het project `package.json` :

```json
"@floodgate/fg-client-sdk": "~1.0.10"
```

Vereist het vervolgens in de code:

```javascript
const { floodgateClient } = require('@floodgate/fg-client-sdk');
```

## De SDK initialiseren {#initialize}

Roep `createInstance()` één keer aan bij het opstarten van de toepassing:

```javascript
floodgateClient.createInstance(
  {
    adobeIoApiKey: "<YOUR_API_KEY>",
    clientIds: ["<CLIENT_ID_1>", "<CLIENT_ID_2>"],
    env: "PRD",    // Use "STG" for Stage
    featureRequestHttpParams: {
      timeout: 60 * 1000  // Optional: request timeout in ms
    },
    ingestAnalyticsHttpParams: {
      timeout: 5 * 1000   // Optional: analytics timeout in ms
    }
  },
  function(cb) {
    // Fetch a fresh service token from IMS and pass it in the callback
    cb(null, SERVICE_TOKEN);
  },
  function() {
    return true;  // Return false to disable analytics
  },
  function(response) {
    // Called when the SDK initializes successfully
    console.log("SDK initialized");
  },
  function(err) {
    // Called if initialization fails
    console.error("SDK init error:", err);
  }
);
```

## Functiemarkeringen ophalen {#retrieve-features}

De vlaggen van de eigenschap zijn asynchroon teruggekeerd in een callback. Kies de juiste methode op basis van uw gebruikerscontext.

### Geverifieerde gebruiker {#authenticated-user}

```javascript
floodgateClient.getFeatures(
  {
    userAccessToken: "<USER_ACCESS_TOKEN>",
    visitorId: "<VISITOR_ID>",
    clientId1: "<CLIENT_ID>",
    meta: true
  },
  function(err, features) {
    if (err) {
      // Handle error and serve default experience
      return;
    }
    const isEnabled = floodgateClient.isFeatureEnabled(features, "MY_FEATURE_FLAG");
    // Serve experience based on isEnabled
  }
);
```

### Anonieme gebruiker {#anonymous-user}

Wanneer geen teken van de gebruikerstoegang beschikbaar is, gebruik een versiemarkering of laat het teken weg om full-rollout versies te ontvangen:

```javascript
floodgateClient.getFeatures(
  {
    releaseFlag: "<RELEASE_FLAG>",
    visitorId: "<VISITOR_ID>",
    clientId1: "<CLIENT_ID>",
    meta: false
  },
  callback
);
```

### Standaard volledige-rollout versies {#default-releases}

Wanneer noch een toegangstoken noch een versiemarkering wordt verstrekt, keert SDK eigenschappen in **Volledige Staat van de Uitvoer** terug of **3&rbrace; staat van de Basislijn &lbrace;:**

```javascript
floodgateClient.getFeatures(
  {
    clientId1: "<CLIENT_ID>",
    visitorId: "<VISITOR_ID>",
    meta: false
  },
  callback
);
```

## Controleren of een functie is ingeschakeld {#check-feature}

```javascript
const isEnabled = floodgateClient.isFeatureEnabled(features, "MY_FEATURE_FLAG");

if (isEnabled) {
  // Serve the new experience
} else {
  // Serve the default experience
}
```

## Foutopsporingsregistratie inschakelen {#debug-logging}

Als u uitgebreide SDK-logboeken wilt inschakelen, geeft u een loggerinstantie op foutopsporingsniveau door wanneer u `createInstance()` aanroept:

```javascript
const bunyan = require('bunyan');
const logger = bunyan.createLogger({ name: "fg", sourceType: "SDK", level: "debug" });

floodgateClient.createInstance(
  { ..., log: logger },
  ...
);
```

## Zie ook {#see-also}

* [Opmerkingen bij de release Node.js SDK](nodejs-sdk-release-notes.md)
* [SDK&#39;s](../../integrate/sdks.md)
* [Abonneren op de API-toepassing](../../integrate/subscribe-to-api-application.md)
* [Integratiestappen](../../integrate/integration-steps.md)
