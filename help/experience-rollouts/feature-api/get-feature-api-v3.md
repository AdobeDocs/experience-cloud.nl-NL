---
title: GET Feature API V3
description: API-referentie voor de Experience Rollouts-API V3, die wordt gebruikt om functiemarkeringen voor webtoepassingen en mobiele toepassingen op te halen.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 1%

---


# GET Feature API V3 {#get-feature-api-v3}

De functie-API V3 is het primaire eindpunt voor het ophalen van functiemarkeringen in webtoepassingen en mobiele toepassingen. Het keert de eigenschappen terug en geeft een gebruiker vrij verkiesbaar voor, op hun identiteit en de publieksregels die in de console worden gevormd.

**Eindpunt:** `GET {HOST}/fg/api/v3/feature`

Gebruik `https://p13-stage.adobe.io` voor Stage en `https://p13n.adobe.io` voor Production.

## Verzoek {#request}

### Aanvraagkoppen {#request-headers}

| Koptekst | Type | Beschrijving | Vereist |
|---|---|---|---|
| `x-api-key` | String | De API-sleutel van uw toepassing vanuit de Adobe Developer Console. Moet afzonderlijk worden ingericht voor werkgebied en productie. | Ja |
| `Authorization` | String | **niet vereist** voor niet voor authentiek verklaarde scenario&#39;s. Gebruik `Bearer <AccessToken>` voor geverifieerde gebruikers. Gebruik `Bearer <ServiceToken>` voor SDK-caching-scenario&#39;s aan de serverzijde. | Nee |
| `x-adobe-uuid` | String | Een unieke apparaat-id van de bezoeker. Wordt gebruikt om het percentage voor rollout voor niet-geverifieerde gebruikers te ondersteunen en de bestendigheid van sessies en niet-geverifieerde overgangen te behouden. | Nee |

### Query-parameters {#query-parameters}

| Parameter | Type | Beschrijving | Vereist |
|---|---|---|---|
| `clientId` | String | De client-id van uw toepassing, zoals vermeld in de Experience Rollouts-console. | Ja |
| `ignore_rf` | Boolean | Als `true` , worden de releasemarkeringen genegeerd en worden alle releases voor de client geretourneerd. Standaard: `false`. | Nee |
| `rf` | String | Release-markering. Wordt alleen gebruikt wanneer `ignore_rf` `false` is. | Nee |
| `meta` | Boolean | Als `true`, meta-gegevens voor elke eigenschap in de reactie wordt omvat, teruggekeerd als sleutel-waarde paar waar de waarde Base64-Gecodeerd is. Standaard: `false`. | Nee |
| `userId` | String | Vereist een de dienstteken. GUID van de gebruiker voor wie u eigenschapmarkeringen wilt terugwinnen. | Nee |
| *de parameters van de Context* | NVT | Om het even welke vraagparameter die hierboven niet wordt vermeld wordt behandeld als contextvariabele en gebruikt om publieksregels te evalueren. Meerdere waarden doorgeven als `?key1=val1&key2=val2` . Voorbeeld: `?clientLanguage=ja_JP&contractCurrency=JPY` . | Nee |

## Antwoord {#response}

### Antwoordstatuscodes {#response-status}

| Statuscode | Beschrijving |
|---|---|
| `200 OK` | Gegevens van de kenmerkmarkering die zijn geretourneerd in de reactiehoofdtekst. |
| `304 Not Modified` | De ETag door de cliënt wordt overgegaan past de recentste serverstaat aan. Behandel dit als een no-op — geen wijzigingen die van toepassing zijn. |
| `400 Bad Request` | De instructie `clientId` wordt niet geactiveerd of de aanvraag is onjuist geformuleerd. |
| `403 Forbidden` | Ongeldige API-sleutel of de toepassing is niet geabonneerd op de Experience Rollouts API in de Adobe Developer Console. |

### Antwoordheaders {#response-headers}

| Koptekst | Beschrijving |
|---|---|
| `x-request-id` | Een unieke aanvraag-id voor foutopsporing. Neem dit op in alle ondersteuningsverzoeken. |
| `ETag` | Een token dat de huidige serverstatus voor de functies van deze gebruiker vertegenwoordigt. Geef deze waarde door als `If-None-Match` in volgende aanvragen. Als de status niet is gewijzigd, retourneert de API `304` . |
| `x-adobe-fg-poll-interval` | De TTL (in seconden) voor de lokale cache van de client. Roep de API pas opnieuw aan nadat dit interval is verstreken. |

### Responsinstantie {#response-body}

De reactie is een JSON-object met de volgende velden op hoofdniveau:

| Veld | Type | Beschrijving |
|---|---|---|
| `api_version` | String | API-versie. Intern veld — geen verwerking vereist. |
| `json_version` | String | JSON-schemaversie. Intern veld — geen verwerking vereist. |
| `ttl` | Geheel | TTL-cache in seconden. Dezelfde waarde als de antwoordheader `x-adobe-fg-poll-interval` . Standaard: 300. |
| `caching_enabled` | Boolean | Als `true` , vindt functieevaluatie lokaal plaats op de client. Als `false`, gebeurt de evaluatie server-kant op elk verzoek. |
| `client_analytics_params` | Object | Analyseconfiguratie voor de toepassing. Zie [ client_analytics_params gebieden ](#client-analytics-params) hieronder. |
| `releases` | Array | Lijst met releases en functiemarkeringen waarvoor de gebruiker in aanmerking komt. Zie [ vrijgeeft hieronder gebieden ](#releases-fields). |

#### client_analytics_params, velden {#client-analytics-params}

| Veld | Beschrijving |
|---|---|
| `app_id` | De numerieke id van de toepassing. |
| `safe_event_required` | `true` als het opnieuw toewijzen van gebeurtenissen is ingeschakeld voor deze client. |
| `analytics_required` | Altijd `false` in V3-reacties. |

#### releasevelden {#releases-fields}

| Veld | Beschrijving |
|---|---|
| `release_name` | De naam van de release of functiegroep waarvoor de gebruiker in aanmerking komt. |
| `bit_index` | De releasebitindex. Negatieve waarden geven de status Volledig uitrollen aan. |
| `features` | Array met functiemarkeringssleutels waarvoor de gebruiker in aanmerking komt. Een eigenschapsleutel is teruggekeerd slechts als de gebruiker verkiesbaar is en de vlag in toegelaten staat is. Dit is het primaire veld waarin uw toepassingslogica moet worden ingebouwd. |
| `meta` | Optionele Base64-gecodeerde metagegevens die aan de functie zijn gekoppeld. Decoderen voor gebruik. |
| `release_analytics_params` | Array met metagegevensobjecten voor analyses voor elke in aanmerking komende functie. Zie [ release_analytics_params gebieden ](#release-analytics-params) hieronder. In de scenario&#39;s van de Groep van de Controle, is `features` leeg. |

#### release_analytics_params, velden {#release-analytics-params}

| Veld | Type | Beschrijving |
|---|---|---|
| `app_id` | Geheel | Toepassings-id. |
| `release_id` | Geheel | Release-id. |
| `bit_index` | Geheel | Geen bitindex. Vervangen. |
| `variant_id` | Geheel | `0` als de gebruiker zich in de Controlegroep bevindt; anders niet-nul. |
| `feature_id` | Geheel | Interne functie-id. |
| `f_key` | String | Functiemarkering. |

## Voorbeeldverzoek en -antwoord {#sample}

### Voorbeeldverzoek {#sample-request}

```http
GET /fg/api/v3/feature?clientId=MyWebApp&meta=true HTTP/1.1
Host: p13n.adobe.io
Authorization: Bearer <ACCESS_TOKEN>
x-api-key: <YOUR_API_KEY>
If-None-Match: <ETAG>
```

### Monsterrespons — gebruiker in testgroep {#sample-response-test}

```json
{
  "api_version": "0.1",
  "json_version": "0.1",
  "clients": {
    "MyWebApp": {
      "analyticsVersion": "2.0",
      "client_analytics_params": {
        "app_id": 1378,
        "safe_event_required": false,
        "analytics_required": false
      },
      "releases": [
        {
          "bit_index": -160,
          "release_name": "||features||",
          "features": ["ff1", "ff2", "ff3"],
          "release_analytics_params": [
            {
              "app_id": 1378,
              "release_id": -1,
              "bit_index": -160,
              "variant_id": 10040476,
              "feature_id": 26059,
              "f_key": "ff1",
              "analytics_required": true
            }
          ]
        }
      ]
    }
  },
  "ttl": 60
}
```

### Monsterreactie — gebruiker in controlegroep {#sample-response-control}

Wanneer een gebruiker deel uitmaakt van de controlegroep, is de array `features` leeg en is de waarde `variant_id` is `0` :

```json
{
  "api_version": "0.1",
  "json_version": "0.1",
  "clients": {
    "MyWebApp": {
      "releases": [
        {
          "bit_index": -160,
          "release_name": "||features||",
          "features": [],
          "release_analytics_params": [
            {
              "app_id": 1378,
              "release_id": -1,
              "bit_index": -160,
              "variant_id": 0,
              "feature_id": 26059,
              "f_key": "ff1"
            }
          ]
        }
      ]
    }
  },
  "ttl": 60
}
```

## Zie ook {#see-also}

* [GET Feature API V2](get-feature-api-v2.md)
* [Webtoepassingen](../guides/integrate/web-applications.md)
* [Mobiele toepassingen](../guides/integrate/mobile-applications.md)
* [Integratiestappen](../guides/integrate/integration-steps.md)
