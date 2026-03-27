---
title: Integratiehandleiding voor Java SDK
description: Leer hoe u de Experience Rollouts Java SDK kunt integreren in uw back-endservice om functiemarkeringen op te halen en te evalueren.
exl-id: 7c12bd6c-1883-4f1c-985f-a2b0432e61ce
source-git-commit: 2a946868f58e25f8aafbf3ccfcf6571e7d0d8d20
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Integratiehandleiding voor Java SDK {#java-sdk-integration-guide}

De Experience Rollouts Java SDK is een bibliotheek aan serverzijde die eigenschapvlaggegevens plaatselijk in het voorgeheugen onderbrengt en vlaggen zonder een synchrone API vraag op elke aanvraag evalueert. Deze handleiding geldt voor de huidige SDK (4.x).

## Vereisten {#prerequisites}

Voordat u de Java SDK gaat integreren, moet u controleren of u beschikt over:

* JDK 11 of hoger (vereist vanaf SDK versie 3.0.0; eerdere versies ondersteunen JDK 8+)
* Een op Maven gebaseerd bouwsysteem
* Een **API sleutel** en **de dienstteken** cliëntidentiteitskaart van uw project van Adobe Developer Console — de steun van Rollouts van de Ervaring van het contact om uw gevoegde op lijst van gewenste personen cliëntidentiteitskaart te hebben
* Uw **toepassings cliënt IDs** die in de console van Rollouts van de Ervaring wordt geregistreerd — zie [ Onboard uw toepassing ](../../applications/onboard-your-application.md)

## De Geweven afhankelijkheid toevoegen {#maven-dependency}

Voeg de Experience Rollouts Java SDK toe aan de `pom.xml` van uw project:

```xml
<dependency>
  <groupId>com.adobe.cloudtech</groupId>
  <artifactId>fg-client-sdk</artifactId>
  <version>4.0.6</version>
</dependency>
```

## De SDK initialiseren {#initialize}

De SDK wordt eenmaal geïnitialiseerd bij het opstarten van de toepassing met behulp van `FloodgateClient.createInstance()` . De methode maakt gebruik van een `FloodgateConfiguration` -object dat u met de configuratiebuilder maakt.

### Implementeer de dienst symbolische callback {#service-token-callback}

SDK gebruikt een callback interface om een vers de dienstteken bij runtime terug te winnen:

```java
private class FgConfigCallBack implements FGConfigBaseCallBack {

  @Override
  public String getIMSServiceToken() {
    // Fetch and return a valid service token
  }

  @Override
  public boolean isAnalyticsEnabled() {
    return false; // Set to true to enable analytics
  }
}
```

### Het configuratieobject maken {#configuration}

Gebruik de configuratiebuilder om de SDK in te stellen:

```java
FloodgateConfiguration configuration = FloodgateConfiguration.FloodgateConfigurationBuilder
    .aFloodgateConfiguration(
        FgEnv.PRD,                   // Use FgEnv.STG for Stage
        "<YOUR_API_KEY>",
        Set.of("<CLIENT_ID_1>", "<CLIENT_ID_2>"),
        new FgConfigCallBack(),
        CallType.ASYNC
    )
    .withRetryPolicy(retryPolicy)    // Optional: defaults to 5 retries, 10s interval
    .build();
```

Gebruik `FgEnv.STG` voor de Stage-omgeving en `FgEnv.PRD` voor Production.

### De clientinstantie maken {#client-instance}

```java
FloodgateClient fgClient = FloodgateClient.createInstance(configuration);
```

## Functiemarkeringen ophalen {#retrieve-features}

### Geverifieerde gebruiker {#authenticated-user}

Gebruik een IMS-toegangstoken om functiemarkeringen voor de huidige gebruiker op te halen:

```java
GetFeatureRequest request = GetFeatureRequestBuilder
    .aGetFeatureRequest("<CLIENT_ID>")
    .withAccessToken("<USER_ACCESS_TOKEN>")
    .withContext(context)
    .build();

FeaturesResponse[] features = fgClient.getFeatures(request);
```

### Anonieme gebruiker {#anonymous-user}

Voor niet-geverifieerde gebruikers geeft u een bezoeker-id en uw service-token door:

```java
GetFeatureRequest request = GetFeatureRequestBuilder
    .aGetFeatureRequest("<CLIENT_ID>")
    .withServiceToken("<SERVICE_TOKEN>")
    .withVisitorId("<VISITOR_ID>")
    .withContext(context)
    .build();

FeaturesResponse[] features = fgClient.getFeatures(request);
```

### Een specifieke functiemarkering of -release ophalen {#specific-feature}

Om één enkele eigenschapvlag door sleutel terug te winnen:

```java
GetFeatureRequest request = GetFeatureRequestBuilder
    .aGetFeatureRequest("<CLIENT_ID>")
    .withAccessToken("<ACCESS_TOKEN>")
    .withFeatureKey("<FEATURE_KEY>")
    .build();
```

Vervang `.withFeatureKey()` door `.withReleaseKey()` om op te halen via de releasesleutel.

## Controleren of een functie is ingeschakeld {#check-feature}

```java
boolean isEnabled = FloodgateClient.isFeatureEnabled(features, "MY_FEATURE_FLAG");

if (isEnabled) {
  // Serve the new experience
} else {
  // Serve the default experience
}
```

Voor op vrijgave gebaseerde controles:

```java
boolean isEnabled = FloodgateClient.isFeatureEnabled(features, "MY_RELEASE", "MY_FEATURE_FLAG");
```

## Cachebeheer {#cache-management}

De de eigenschapvlaggegevens van de eigenschapmarkering van de geheime voorgeheugens van SDK en verfrist het op een opiniepeilingsinterval dat per toepassing in de console wordt geplaatst. Een cache-vernieuwing op aanvraag activeren:

```java
fgClient.refreshClientCache("<CLIENT_ID>");
```

### Niet-cachebare clients {#non-cacheable}

Voor niet-cachebare clients roept `getFeature()` elke keer een live API aan. De SDK gaat verder met opiniepeilingen op de achtergrond en schakelt over naar cache-gebaseerde serving wanneer de client cacheable wordt. Ondersteund vanaf SDK versie 0.8.

## Configuratieopties {#configuration-options}

De volgende optionele configuratiemethoden zijn beschikbaar in de builder:

| Optie | Methode | Beschrijving |
|---|---|---|
| Altijd cache gebruiken | `.alwaysCache()` | Hiermee wordt het in cache plaatsen van de API omzeild; het wordt gebruikt voor markeringen zonder publieksregels |
| Cache uitschakelen | `.neverCache()` | Schakelt standaardcaching onbruikbaar; nuttig voor de logica van de douanecache verfrist |
| Aangepaste HTTP-client | `.withHttpClient(client)` | Gebruik uw eigen HTTP-client |
| Aangepaste uitvoerder | `.withScheduledExecutorService(executor)` | Gebruik uw eigen geplande uitvoerder voor achtergrondopiniepeiling |
| Inclusief besturingsgroep | `.includeControlGroup()` | Hiermee worden de gegevens van de controlegroep in de functiereactie geretourneerd |

## Fouten verwerken {#error-handling}

Terugloop `getFeatures()` -aanroepen om SDK-uitzonderingen af te vangen:

```java
try {
  features = fgClient.getFeatures(request);
} catch (FgClientException e) {
  int statusCode = e.getStatusCode();
  // Handle error and serve default experience
} catch (FgInitException e) {
  e.printStackTrace();
}
```

## Zie ook {#see-also}

* [Opmerkingen bij de release Java SDK](java-sdk-release-notes.md)
* [SDK&#39;s](../../integrate/sdks.md)
* [Integratiestappen](../../integrate/integration-steps.md)
