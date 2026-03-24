---
title: API voor kenmerkvlaggen
description: API-naslaggids voor de functie Experience Rollouts geeft de API voor het beheer van fouten weer, inclusief eindpunten voor het ophalen, maken, bijwerken en verwijderen van functiemarkeringen voor een toepassing.
source-git-commit: 8a92b7a3e8c52da8bb2474f52c831e159420b878
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---


# API voor kenmerkvlaggen {#feature-flags-management-api}

Met de API voor het beheer van functiemarkeringen kunt u programmatisch functiemarkeringen voor uw toepassingen maken, lezen, bijwerken en verwijderen in Experience Rollouts.

**De weg van de Basis:** `/m/api/v1/mgmt/feature`

Alle verzoeken vereisen de kopballen die in de [&#x200B; worden beschreven gemeenschappelijke vereisten &#x200B;](feature-management-apis-overview.md#common-requirements).

## Alle functiemarkeringen ophalen {#get-all-features}

Hiermee worden alle eigenschapmarkeringen voor een opgegeven toepassing opgehaald.

| | |
|---|---|
| **Eindpunt** | `GET /m/api/v1/mgmt/feature` |
| **Methode** | GET |

### Query-parameters {#get-all-query-params}

| Parameter | Type | Beschrijving | Vereist |
|---|---|---|---|
| `clientId` | Geheel | Numerieke id van de toepassing. Zie [&#x200B; cliëntidentiteitskaart &#x200B;](get-client-id.md) krijgen. Vereist als `imsClientId` niet is opgegeven. | Voorwaardelijk |
| `imsClientId` | String | Clientid met tekenreeksindeling van de toepassing. Vereist als `clientId` niet is opgegeven. | Voorwaardelijk |
| `nonReleaseFeature` | Boolean | Ingesteld op `true` om onafhankelijke functiemarkeringen op te nemen die niet aan een groep of versie zijn gekoppeld. Vereist voor op API gebaseerde workflows. | Ja |

### Antwoord {#get-all-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie bevat een lijst van de voorwerpen van de eigenschapmarkering. |

De hoofdtekst van de reactie bevat een array `features` . Elk element is een voorwerp van de eigenschapvlag met de gebieden die in de [&#x200B; worden beschreven FontDTO objecten verwijzing &#x200B;](#featuredto-object).

**Antwoord van de Steekproef:**

```json
{
  "features": [
    {
      "id": 22079,
      "name": "new.FF.1",
      "clientId": 1191,
      "state": "enabled",
      "description": "first feature flag",
      "release": { "id": 2631, "name": "FF.group", "status": "SAVED" },
      "audience": null,
      "params": { "label": "new FF 1", "rolloutType": "manual" }
    },
    {
      "id": 22080,
      "name": "new.FF.2",
      "clientId": 1191,
      "state": "enabled",
      "description": "second feature flag",
      "audience": [
        {
          "id": 10034665,
          "criteria": { "and": [{ "operator": "EQ", "attr": "LOCALE", "val": "EN" }] }
        }
      ]
    }
  ]
}
```

## Markering voor functie ophalen via id {#get-feature-by-id}

Haalt één functiemarkering met de numerieke id op.

| | |
|---|---|
| **Eindpunt** | `GET /m/api/v1/mgmt/feature/{featureId}` |
| **Methode** | GET |

### Antwoord {#get-by-id-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. Het lichaam van de reactie is één enkel [&#x200B; FeatureDTO voorwerp &#x200B;](#featuredto-object). |
| `400` | Ongeldige functie-id. |

## Functiemarkering maken {#create-feature}

Maakt een nieuwe functiemarkering.

| | |
|---|---|
| **Eindpunt** | `POST /m/api/v1/mgmt/feature` |
| **Methode** | POST |

### Aanvragingsinstantie {#create-request-body}

Het verzoeklichaam is a [&#x200B; voorwerp FeatureDTO &#x200B;](#featuredto-object). De volgende velden zijn vereist voor het maken:

| Veld | Vereist | Notities |
|---|---|---|
| `name` | Ja | Functiemarkering. Maximaal 50 tekens. Patroon: `^[a-zA-Z0-9_.-]*$` |
| `clientId` | Ja | Numerieke toepassings-id. Zie [&#x200B; cliëntidentiteitskaart &#x200B;](get-client-id.md) krijgen. |
| `state` | Ja | `"enabled"` of `"disabled"` |

### Antwoord {#create-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie bevat `{ "generatedFeatureId": <id> }` . |
| `400` | Ongeldige lading. |
| `403` | Onvoldoende machtigingen voor deze client- of publieksregel. |
| `417` | Gebruikers met de rol Ontwikkelaar kunnen een functie niet opslaan met een openbare regel. Er is ten minste één publieksregel vereist. |

**verzoek van de Steekproef:**

```json
{
  "name": "my-new-feature",
  "clientId": 1191,
  "state": "disabled",
  "description": "A new feature flag",
  "meta": "VGVzdA==",
  "audience": [
    {
      "criteria": {
        "and": [{ "operator": "EQ", "attr": "COUNTRY", "category": "default", "ruleId": 1, "val": "US" }]
      }
    }
  ],
  "variations": [{ "variantPercentage": 100, "variantName": "Variation 1" }],
  "params": { "label": "My New Feature", "tags": [] }
}
```

## Functiemarkering bijwerken {#update-feature}

Werkt een bestaande functiemarkering bij. Geef het volledige [&#x200B; voorwerp FeatureDTO &#x200B;](#featuredto-object) met inbegrip van het `id` gebied door.

| | |
|---|---|
| **Eindpunt** | `PUT /m/api/v1/mgmt/feature` |
| **Methode** | PUT |

### Antwoord {#update-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is het bijgewerkte voorwerp FeatureDTO. |
| `400` | Ongeldige lading. |
| `403` | Onvoldoende machtigingen. |
| `417` | Conflict tussen gelijktijdige updates. Haal eerst de huidige functie op en probeer het opnieuw met de nieuwste `version` waarde van `params` . |

## Functiemarkering verwijderen {#delete-feature}

Verwijdert een functiemarkering met de numerieke id.

| | |
|---|---|
| **Eindpunt** | `DELETE /m/api/v1/mgmt/feature/{featureId}` |
| **Methode** | DELETE |

### Antwoord {#delete-response}

| Status | Beschrijving |
|---|---|
| `204` | Geslaagd. Geen responsorgaan. |
| `403` | Onvoldoende machtigingen. |

## Verwijzing naar FeatureDTO-object {#featuredto-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Functiemarkering-id. Vereist slechts voor updatevraag. | Voorwaardelijk |
| `name` | String | Functiemarkering (geretourneerd in API-reacties). Maximaal 50 tekens. Patroon: `^[a-zA-Z0-9_.-]*$` | Ja (maken) |
| `clientId` | Geheel | Numerieke toepassings-id. | Ja |
| `state` | String | `"enabled"` of `"disabled"` | Ja |
| `meta` | String | Base64-gecodeerde die meta-gegevens met de eigenschap in API reacties worden teruggekeerd. Max. 1024 tekens. | Nee |
| `description` | String | Beschrijving weergeven. Max. 225 tekens. | Nee |
| `audience` | Array | Lijst met publieksregels. Zie [&#x200B; voorwerp FeatureRule &#x200B;](#featurerule-object). Het gebruik [&#x200B; krijgt gewenste publiekscriteria &#x200B;](get-audience-criteria.md) om dit te produceren. | Nee |
| `variations` | Array | Lijst van varianten. Max. 3. Zie [&#x200B; voorwerp FeatureVariation &#x200B;](#featurevariation-object). | Nee |
| `params` | Object | Aanvullende metagegevens. Ondersteunde toetsen: `label` (display name in UI), `tags` (string array). | Nee |
| `release` | Object | Geen/groep-koppeling. `null` als de markering zich niet in een groep bevindt. Alleen-lezen. | Nee |

### Object FeatureVariation {#featurevariation-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Variatie-id. Vereist slechts voor updatevraag. | Voorwaardelijk |
| `variantName` | String | Naam variant. Vaste waarden: `"Variation 1"` , `"Variation 2"` , `"Variation 3"` . | Ja |
| `variantPercentage` | Decimaal | Percentage van het publiek dat deze variant ontvangt. Moet groter zijn dan 0 en niet meer dan 100, met maximaal 2 decimalen. | Ja |

### Object FeatureRule {#featurerule-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Regel-id. Vereist slechts voor updatevraag. Instellen op `null` wanneer een nieuwe regel wordt toegevoegd. | Voorwaardelijk |
| `criteria` | Object | Condition-object dat de publieksregel definieert. Zie [&#x200B; voorwerp van de Voorwaarde &#x200B;](#condition-object). | Ja |

### Object Condition {#condition-object}

| Veld | Type | Beschrijving |
|---|---|---|
| `and` | Array\&lt;Condition\> | Alle voorwaarden moeten waar zijn. |
| `or` | Array\&lt;Condition\> | Ten minste één voorwaarde moet waar zijn. |
| `not` | Voorwaarde | Deze voorwaarde moet onwaar zijn. |
| `attr` | String | Het gebruikerskenmerk dat moet worden geëvalueerd (bijvoorbeeld `COUNTRY` , `LOCALE` ). |
| `operator` | String | Vergelijkingsoperator (bijvoorbeeld `EQ` , `IN` , `LT` ). |
| `val` | String | De waarde die moet worden vergeleken met. |
| `meta` | Object | Metagegevens van optionele voorwaarde. `desc` wordt het weergavelabel in de gebruikersinterface ingesteld. |

In elke voorwaarde moet een van `and`, `or` of `not` of een combinatie van `attr` , `operator` en `val` worden opgegeven.

## Zie ook {#see-also}

* [Overzicht van API&#39;s voor functiebeheer](feature-management-apis-overview.md)
* [Beheer van patch-API](management-patch-api.md)
* [Client-id voor een toepassing ophalen](get-client-id.md)
* [Kies de gewenste publiekscriteria](get-audience-criteria.md)
