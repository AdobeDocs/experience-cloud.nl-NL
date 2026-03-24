---
title: GET Feature API V2
description: API-referentie voor de Experience Rollouts-API V2, die wordt gebruikt om functiemarkeringen voor bureaubladtoepassingen op te halen.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---


# GET Feature API V2 {#get-feature-api-v2}

De functie-API V2 is ontworpen voor de integratie van desktoptoepassingen. De functie haalt functiemarkeringen op en geeft gegevens voor de geverifieerde gebruiker vrij. Deze functie ondersteunt productcode en productversie als de toepassings-id naast een standaard client-id.

**Eindpunt:** `GET {HOST}/fg/api/v2/feature`

Gebruik `https://p13-stage.adobe.io` voor Stage en `https://p13n.adobe.io` voor Production.

## Verzoek {#request}

### Aanvraagkoppen {#request-headers}

| Koptekst | Type | Beschrijving | Vereist |
|---|---|---|---|
| `x-api-key` | String | De API-sleutel van uw toepassing vanuit de Adobe Developer Console. Moet afzonderlijk worden ingericht voor werkgebied en productie. | Ja |
| `Authorization` | String | `Bearer <AccessToken>` of `Bearer <ServiceToken>` . | Ja |
| `x-adobe-uuid` | String | Een unieke apparaat-id van de bezoeker. Gebruikt voor percentalrollout in niet voor authentiek verklaarde scenario&#39;s en om zittingskleverigheid te handhaven. | Nee |

### Query-parameters {#query-parameters}

| Parameter | Type | Beschrijving | Vereist |
|---|---|---|---|
| `clientId` | String | De client-id van de toepassing, zoals vermeld in de console Experience Rollouts. U kunt meerdere waarden doorgeven: `clientId=C1&clientId=C2` . | Nee |
| `p` | String | Product, versie, platform, landinstellingstekenreeks (PVPL-indeling). Voorbeeld: `PHSP:17.0:WIN:en_US` . U kunt meerdere waarden doorgeven: `p=PHSP:17.0:WIN:en_US&p=PPRO:8:WIN:en_US` . Bij de evaluatie worden alleen productcode en productversie gebruikt. | Nee |
| `meta` | Boolean | Als `true`, worden de Base64-Gecodeerde meta-gegevens teruggegeven voor elke eigenschap. Standaard: `false`. | Nee |
| *de parameters van de Context* | NVT | Om het even welk extra zeer belangrijk-waardepaar wordt behandeld als contextvariabele voor de evaluatie van de publieksregel. Voorbeeld: `clientLanguage=ja_JP&contractCurrency=JPY` . | Nee |

>[!NOTE]
>
>Ten minste een van `clientId` of `p` is vereist om de toepassing te identificeren.

## Antwoord {#response}

### Antwoordstatuscodes {#response-status}

| Statuscode | Beschrijving |
|---|---|
| `200 OK` | Gegevens van de kenmerkmarkering die zijn geretourneerd in de reactiehoofdtekst. |
| `304 Not Modified` | De ETag past de huidige serverstaat aan. Behandel als een no-op — geen wijzigingen van toepassing. |
| `401 Unauthorized` | De machtigingstoken is ongeldig. |

### Antwoordheaders {#response-headers}

| Koptekst | Beschrijving |
|---|---|
| `x-request-id` | Een unieke aanvraag-id voor foutopsporing. Neem dit op in alle ondersteuningsverzoeken. |
| `ETag` | Token dat de huidige eigenschapstaat voor de gebruiker vertegenwoordigt. Doorgeven als `If-None-Match` in volgende aanvragen. Retourneert `304` indien ongewijzigd. |
| `x-adobe-fg-poll-interval` | TTL in seconden voor het lokale geheime voorgeheugen van de cliënt. Roep de API pas opnieuw aan nadat dit interval is verstreken. |

### Responsinstantie {#response-body}

De reactie is een JSON-object met de volgende velden op hoofdniveau:

| Veld | Type | Beschrijving |
|---|---|---|
| `api_version` | String | API-versie. Intern veld — geen verwerking vereist. |
| `json_version` | String | JSON-schemaversie. Intern veld — geen verwerking vereist. |
| `ttl` | Geheel | TTL-cache in seconden. Standaard: 300. |
| `clients` | Object | Kaart van cliënt IDs (of koorden PVPL) aan hun versiegegevens. Elke sleutel bevat de hieronder beschreven velden. |

#### Reactievelden per client {#per-client-fields}

| Veld | Beschrijving |
|---|---|
| `releases` | Array met releases waarvoor de gebruiker in aanmerking komt. Zie [ vrijgeeft hieronder gebieden ](#releases-fields). |
| `client_analytics_params` | Configuratieobject Analytics. Zie [ client_analytics_params gebieden ](#analytics-fields) hieronder. |

#### releasevelden {#releases-fields}

| Veld | Beschrijving |
|---|---|
| `release_name` | Naam van de release of functiegroep. |
| `bit_index` | Geen bitindex. Vervangen. Kan `null` of negatief zijn, afhankelijk van de releasestatus. |
| `features` | Array met functiemarkeringssleutels waarvoor de gebruiker in aanmerking komt. Een functietoets wordt alleen weergegeven als de gebruiker hiervoor in aanmerking komt en de markering is ingeschakeld. |
| `meta` | Optionele Base64-gecodeerde metagegevens. Decoderen voor gebruik. |
| `release_analytics_params` | Metagegevens voor Analytics voor subsidiabele functies. In de scenario&#39;s van de Groep van de Controle, is `features` leeg. |

#### release_analytics_params, velden {#release-analytics-params}

| Veld | Type | Beschrijving |
|---|---|---|
| `app_id` | Geheel | Toepassings-id. |
| `release_id` | Geheel | Release-id. |
| `bit_index` | Geheel | Vervangen. |
| `variant_id` | Geheel | `0` als Controlegroep; anders niet-nul. |
| `feature_id` | Geheel | Interne functie-id. |
| `f_key` | String | Functiemarkering. |

#### client_analytics_params, velden {#analytics-fields}

| Veld | Type | Beschrijving |
|---|---|---|
| `app_id` | Geheel | Toepassings-id. |
| `safe_event_required` | Boolean | `true` als het opnieuw toewijzen van gebeurtenissen is ingeschakeld. |
| `analytics_required` | Boolean | `false` als de analyse is uitgeschakeld of bij de standaardstroom; `true` als Kinesis-stroom is ingeschakeld. |

## Voorbeeldverzoek en -antwoord {#sample}

### Voorbeeldverzoek {#sample-request}

```http
GET /fg/api/v2/feature?clientId=MyDesktopApp&p=PHSP:17.0:WIN:en_US&meta=true HTTP/1.1
Host: p13n.adobe.io
Authorization: Bearer <ACCESS_TOKEN>
x-api-key: <YOUR_API_KEY>
If-None-Match: <ETAG>
```

### Monsterreactie {#sample-response}

```json
{
  "api_version": "0.1",
  "json_version": "0.1",
  "clients": {
    "PHSP:17.0:WIN:en_US": {
      "analyticsVersion": "1.0",
      "releases": []
    },
    "MyDesktopApp": {
      "analyticsVersion": "1.0",
      "client_analytics_params": {
        "app_id": 388,
        "safe_event_required": false,
        "analytics_required": false
      },
      "releases": [
        {
          "bit_index": 160,
          "release_name": "||features||",
          "features": ["feature_a", "feature_b"],
          "release_analytics_params": [
            {
              "app_id": 388,
              "release_id": -1,
              "bit_index": 160,
              "variant_id": 10031741,
              "feature_id": 2918,
              "f_key": "feature_a"
            }
          ],
          "meta": []
        }
      ]
    }
  },
  "ttl": 300
}
```

## Zie ook {#see-also}

* [GET Feature API V3](get-feature-api-v3.md)
* [Bureaubladtoepassingen](../guides/integrate/desktop-applications.md)
* [Integratiestappen](../guides/integrate/integration-steps.md)
