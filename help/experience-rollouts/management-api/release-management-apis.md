---
title: Beheer-API's vrijgeven
description: API-naslaggids voor de Experience Rollouts-beheer-API's, inclusief eindpunten voor het ophalen, maken en bewerken van releases en groepen met functies voor meerdere teams.
exl-id: e8d1d025-0645-4cf2-921f-d94c9f71282d
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 2%

---

# Beheer-API&#39;s vrijgeven {#release-management-apis}

Met de releasebeheer-API&#39;s kunt u softwarematig releases en groepen met meerdere teams ophalen, maken en bewerken. Deze APIs gebruiken het v2 beheerseindpunt.

**De weg van de Basis:** `/m/api/v2/mgmt/release`

Alle verzoeken vereisen de kopballen die in de [&#x200B; worden beschreven gemeenschappelijke vereisten &#x200B;](feature-management-apis-overview.md#common-requirements), plus de extra hieronder vermelde kopbal.

## Aanvullende vereiste koptekst {#additional-header}

| Koptekst | Beschrijving | Vereist |
|---|---|---|
| `x-user-context-org` | De numerieke team-id voor uw organisatie. U kunt deze waarde vinden in de Experience Rollouts-console onder uw teaminstellingen. | Ja |

## Release via id ophalen {#get-release}

Haalt één enkele versie of de dwars-teameigenschapgroep door zijn numerieke identiteitskaart op.

| | |
|---|---|
| **Eindpunt** | `GET /m/api/v2/mgmt/release/{id}` |
| **Methode** | GET |

### Query-parameters {#get-query-params}

| Parameter | Type | Beschrijving | Standaard |
|---|---|---|---|
| `includePermissions` | Boolean | Inclusief machtigingen voor het bijwerken of verwijderen van deze versie. | `true` |
| `includeOrg` | Boolean | Omvat organisatieinformatie voor deze versie. | `true` |
| `includeAnalyzeInfo` | Boolean | Analytische gegevens opnemen. | `false` |

### Antwoord {#get-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. Het lichaam van de reactie is een versievoorwerp — zie [&#x200B; de objecten van de Versie verwijzing &#x200B;](#release-object). |
| `400` | Ongeldige release-id of onjuist geformuleerd verzoek. |

## Release maken {#create-release}

Hiermee maakt u een nieuwe release of een groep met functies voor meerdere teams.

| | |
|---|---|
| **Eindpunt** | `POST /m/api/v2/mgmt/release` |
| **Methode** | POST |

### Aanvragingsinstantie {#create-request-body}

Het verzoeklichaam gebruikt het [&#x200B; voorwerp van de Versie &#x200B;](#release-object). Voor het maken moet `status` worden ingesteld op `"SAVED"` voor groepen met functies die verschillende teams vertegenwoordigen (`CROSS_TEAM_FEATURE_GROUP` type) of `"DRAFT"` voor standaardreleases (`RELEASE` type).

**Steekproef — creeer dwars-teameigenschapgroep:**

```json
{
  "params": {
    "rolloutType": "manual",
    "cohortingType": "guid",
    "tags": [],
    "canContextOverridePUP": false,
    "label": "my-cross-team-group"
  },
  "status": "SAVED",
  "type": "CROSS_TEAM_FEATURE_GROUP",
  "name": "my-cross-team-group",
  "description": null,
  "meta": "",
  "variations": [{ "variantPercentage": 100, "variantName": "Variant 1", "features": [] }],
  "audience": [{}],
  "clients": [],
  "pollInterval": 300,
  "org": { "id": "95" },
  "comment": ""
}
```

### Antwoord {#create-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is het gemaakte releaseobject. |
| `400` | Ongeldige lading. |

## Release bewerken {#edit-release}

Werkt een bestaande versie of een groep van de dwars-teameigenschap bij. Geef het volledige releaseobject door, inclusief het veld `id` .

| | |
|---|---|
| **Eindpunt** | `PUT /m/api/v2/mgmt/release/{id}` |
| **Methode** | PUT |

### Antwoord {#edit-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is het bijgewerkte versievoorwerp. |
| `417` | Conflict tussen gelijktijdige updates. De release is gewijzigd tussen GET- en PUT-oproepen. Zoek de huidige release en probeer het opnieuw. |

## Verwijzing naar releaseobject {#release-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Release-id. Vereist slechts voor updatevraag. | Voorwaardelijk |
| `name` | String | Geen naam. Maximaal 50 tekens. Patroon: `^[a-zA-Z0-9_ ,.:()-]*$`. Moet uniek zijn. | Ja |
| `description` | String | Optionele beschrijving. Max. 255 tekens. | Nee |
| `type` | String | `"RELEASE"` voor standaardreleases; `"CROSS_TEAM_FEATURE_GROUP"` voor functiegroepen die gelden voor meerdere teams. | Ja |
| `status` | String | Status Vrijgeven. Voor IMS: `"DRAFT"` bij maken; `"DRAFT"`, `"SAVED"`, `"PUBLISHED"` bij bijwerken. Voor CTFG: `"SAVED"` bij maken; `"SAVED"` , `"PUBLISHED"` bij bijwerken. | Ja |
| `clients` | Array | Toepassingen die aan deze release zijn gekoppeld. Voor elk item zijn `id` (numeriek) en `imsClientId` (tekenreeks) vereist. | Nee |
| `audience` | Array | Lijst met publieksregels. Zie [&#x200B; voorwerp van de Voorwaarde &#x200B;](feature-flags-management-api.md#condition-object). | Nee |
| `variations` | Array | Lijst met variaties. Slechts 1 variatie wordt gesteund tijdens voorlegging. | Vereist voor indiening |
| `params` | Object | Geen parameters. Zie [&#x200B; Gesteunde paramentengebieden &#x200B;](#supported-params). | Vereist voor indiening |
| `org` | Object | Organisatie-object. Moet `id` bevatten. | Nee |

### Ondersteunde parametervelden {#supported-params}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `label` | String | Naam weergeven. Maximaal 50 tekens. | Ja |
| `tags` | Array\&lt;String\> | Optionele tags. Maximaal 50 tekens per stuk. | Nee |
| `canContextOverridePUP` | Boolean | Indien `true` , hebben contextregels voorrang op profielregels. Standaard: `false`. | Ja |
| `isBetaRelease` | Boolean | Indien `true` , wordt dit gemarkeerd als een bètaversie. Standaard: `false`. | Nee |

### Object Variatie {#variation-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Variatie-id. Vereist slechts voor updatevraag. | Voorwaardelijk |
| `variantName` | String | Naam variant. Maximaal 50 tekens. | Ja |
| `variantPercentage` | Dubbel | Percentage van het publiek dat deze variant ontvangt. Waaier: [ 0, 100 ]. | Ja |
| `features` | Array | Functies die in deze variatie zijn opgenomen. Elke vermelding moet `id`, `name`, `clientId` en `state` bevatten. | Nee |

## Zie ook {#see-also}

* [Overzicht van API&#39;s voor functiebeheer](feature-management-apis-overview.md)
* [API voor kenmerkvlaggen](feature-flags-management-api.md)
* [API voor beheer van functiegroepen](feature-group-management-api.md)
