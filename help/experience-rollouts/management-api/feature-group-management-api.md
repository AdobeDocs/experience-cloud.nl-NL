---
title: API voor beheer van functiegroepen
description: API-naslaggids voor de API voor het beheer van de functiegroep Experience, inclusief eindpunten voor het ophalen, maken, bijwerken, verwijderen en beheren van implementatieplannen voor functiegroepen.
source-git-commit: 8a92b7a3e8c52da8bb2474f52c831e159420b878
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 4%

---


# API voor beheer van functiegroepen {#feature-group-management-api}

Met de API voor het beheer van functiegroepen kunt u programmatisch functiegroepen maken, lezen, bijwerken en verwijderen in Experience Rollouts, inclusief geautomatiseerde en A/B-testimplementatieplannen.

**De weg van de Basis:** `/m/api/v1/mgmt/group`

Alle verzoeken vereisen de kopballen die in de [ worden beschreven gemeenschappelijke vereisten ](feature-management-apis-overview.md#common-requirements).

## Alle functiegroepen ophalen {#get-all-groups}

Hiermee worden alle functiegroepen voor uw organisatie opgehaald.

| | |
|---|---|
| **Eindpunt** | `GET /m/api/v1/mgmt/group` |
| **Methode** | GET |

### Query-parameters {#get-all-query-params}

| Parameter | Type | Beschrijving | Vereist |
|---|---|---|---|
| `myOrg` | Boolean | Ingesteld op `true` om organisatie-informatie op te nemen. | Ja |
| `includeClientInfo` | Boolean | Ingesteld op `true` om toepassingsinformatie voor elke groep op te nemen. | Ja |

### Antwoord {#get-all-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is een serie van eigenschapgroep voorwerpen. |

## Objectgroep ophalen op id {#get-group-by-id}

Haalt één functiegroep op aan de hand van de numerieke id.

| | |
|---|---|
| **Eindpunt** | `GET /m/api/v1/mgmt/group/{groupId}` |
| **Methode** | GET |
| **parameter van de Vraag** | `includeAnalyzeInfo=true` (optioneel — voegt analysegegevens toe aan het antwoord) |

### Antwoord {#get-by-id-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is een voorwerp van de eigenschapgroep. |
| `400` | Ongeldige ID functiegroep. |

## Functiegroep maken {#create-group}

Hiermee maakt u een nieuwe functiegroep met een handmatig, automatisch of A/B-testrollouttype.

| | |
|---|---|
| **Eindpunt** | `POST /m/api/v1/mgmt/group` |
| **Methode** | POST |

### Aanvragingsinstantie {#create-request-body}

Het verzoeklichaam gebruikt het [ voorwerp van de eigenschapgroep ](#feature-group-object). `rolloutType` inside `params` is verplicht en bepaalt de structuur van de lading.

**Steekproef — handuitrol:**

```json
{
  "params": {
    "rolloutType": "manual",
    "label": "my-feature-group",
    "tags": [],
    "canContextOverridePUP": false
  },
  "status": "SAVED",
  "type": "group",
  "name": "my.feature.group",
  "description": "A manual feature group",
  "variations": [{ "variantPercentage": 100, "variantName": "Variant 1", "features": [] }],
  "audience": [{ "criteria": { "and": [{ "operator": "EQ", "attr": "COUNTRY", "val": "US", "ruleId": 1, "category": "default" }] } }],
  "clients": [],
  "org": { "id": 95 }
}
```

**Steekproef — geautomatiseerde uitloop:**

```json
{
  "params": { "rolloutType": "automated", "label": "my-automated-group", "tags": [] },
  "status": "SAVED",
  "type": "group",
  "name": "my.automated.group",
  "variations": [{ "variantPercentage": 100, "variantName": "Variant 1", "features": [] }],
  "phaseRollOutPlan": {
    "phaseRollOutBlocks": [
      { "isPhaseBlock": true, "phaseRule": { "audience": [] }, "waitRule": null, "blockId": 1, "blockName": "", "isBlockActivated": false },
      { "isPhaseBlock": false, "phaseRule": null, "waitRule": { "waitDuration": { "val": "2", "unit": "HOURS" } }, "blockId": 2, "blockName": "", "isBlockActivated": false },
      { "isPhaseBlock": true, "phaseRule": { "audience": [] }, "waitRule": null, "blockId": 3, "blockName": "", "isBlockActivated": false }
    ],
    "rollOutPlanState": "DRAFT"
  },
  "clients": [],
  "org": { "id": 95 }
}
```

### Antwoord {#create-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is het gecreeerde voorwerp van de eigenschapgroep. |
| `400` | Ongeldige nuttige lading — zie [ foutenmeldingen ](#error-messages) voor details. |
| `403` | Onvoldoende machtigingen. |

## Functiegroep bijwerken {#update-group}

Werkt een bestaande functiegroep bij. Geef dezelfde structuur door als de hoofdtekst van de aanvraag voor het maken, inclusief het veld `id` .

| | |
|---|---|
| **Eindpunt** | `PUT /m/api/v1/mgmt/group` |
| **Methode** | PUT |

### Antwoord {#update-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is het bijgewerkte voorwerp van de eigenschapgroep. |
| `400` | Ongeldige lading. |
| `403` | Onvoldoende machtigingen. |

## Een implementatieplan onderbreken, hervatten of afbreken {#pause-resume-abort}

Hiermee wordt de uitvoering van een geautomatiseerd implementatieplan of een implementatieplan voor A/B-tests tijdens de uitvoering bepaald.

| Actie | Endpoint |
|---|---|
| **Hervatten** | `POST /m/api/v1/mgmt/phaserollout/resume` |
| **Pauze** | `POST /m/api/v1/mgmt/phaserollout/pause` |
| **afbreken** | `POST /m/api/v1/mgmt/phaserollout/abort` |

### Aanvragingsinstantie {#control-request-body}

```json
{
  "entityId": 10282,
  "fgEntityType": "GROUP"
}
```

### Antwoord {#control-response}

Retourneert `true` als de bewerking is geslaagd.

## Functiegroep verwijderen {#delete-group}

Verwijdert een functiegroep met zijn numerieke id.

| | |
|---|---|
| **Eindpunt** | `DELETE /m/api/v1/mgmt/group/{groupId}` |
| **Methode** | DELETE |

### Antwoord {#delete-response}

| Status | Beschrijving |
|---|---|
| `204` | Geslaagd. Geen responsorgaan. |
| `403` | Onvoldoende machtigingen. |

## Verwijzing naar functiegroep-object {#feature-group-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Functiegroep-ID. Vereist slechts voor updatevraag. | Voorwaardelijk |
| `name` | String | Sleutel voor functiegroep. Maximaal 50 tekens. Patroon: `^[a-zA-Z0-9_.-]*$` | Ja (maken) |
| `clients` | Array | Toepassingen die aan de groep zijn gekoppeld. Elke vermelding moet `id` en `imsClientId` bevatten. | Ja |
| `status` | String | `"SAVED"` of `"PUBLISHED"` | Ja |
| `type` | String | Altijd `"group"` voor groepen functies. | Ja |
| `org` | Object | Organisatie-details. Moet `id` bevatten. | Ja |
| `params` | Object | Groepsparameters `rolloutType` is verplicht (`"manual"`, `"automated"` of `"ab-testing"`). Biedt ook ondersteuning voor `label` en `tags` . | Ja |
| `audience` | Array | Regels voor het publiek voor handmatige rollout-typen. | Nee |
| `variations` | Array | Lijst van varianten. Zie [ voorwerp FeatureGroupVariation ](#featuregroupvariation-object). | Nee |
| `phaseRollOutPlan` | Object | Uitrolplan fase. Vereist voor geautomatiseerde en A/B-testtypen. Zie [ voorwerp PhaseRollOutPlan ](#phaserolloutplan-object). | Voorwaardelijk |
| `description` | String | Optionele weergavebeschrijving. Max. 225 tekens. | Nee |

### Object FeatureGroupVariation {#featuregroupvariation-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `id` | Geheel | Variatie-id. Vereist slechts voor updatevraag. | Voorwaardelijk |
| `variantName` | String | Naam variant. Hardcoded to `"Variant 1"`. | Ja |
| `variantPercentage` | Decimaal | Percentage van het publiek dat deze variant ontvangt. Moet groter zijn dan 0 en niet groter dan 100. | Ja |

### PhaseRollOutPlan, object {#phaserolloutplan-object}

| Veld | Type | Beschrijving | Vereist |
|---|---|---|---|
| `phaseRollOutBlocks` | Array | Geordende lijst met faseblokken en wachtblokken. Het laatste blok moet een faseblok zijn. | Ja |
| `rollOutPlanState` | String | `"DRAFT"` , `"RUNNING"` , `"PAUSED"` of `"ABORTED"` | Ja |

Elk blok in `phaseRollOutBlocks` is of a **faseblok** (`isPhaseBlock: true`) die a `phaseRule` met publiekscriteria bevatten, of a **wacht blok** (`isPhaseBlock: false`) die a `waitRule` met of a `waitDuration` (relatief) of `executionDate` (vaste timestamp) bevatten.

## Foutberichten {#error-messages}

| Voorwaarde | Status | Foutbericht |
|---|---|---|
| Ongeldige of lege naam | 400 | `Error: Invalid value for release name.` |
| Lege publiekscriteria | 400 | `Error: Release is not valid` |
| Meerdere variaties voor geautomatiseerde tekst | 400 | `Error: Feature variation is not valid. Variation name should be unique across variations` |
| Gepubliceerde groep zonder clients | 400 | `Error: At least one client must be associated with enabled feature group.` |
| Laatste blok in plan is geen faseblok | 400 | `Error: The last block in the Phase Rollout plan should be phase block` |
| Blok timings uit orde wachten | 400 | `Error: Wait block timings are not in order in the phase rollout plan` |
| Inconsistente wachtbloktypen | 400 | `Error: Wait block should be of same type.` |
| Een geactiveerd faseblok bewerken | 400 | `Error: Activated phase block should not be changed` |
| Leeg rollout-type | 400 | `Error: Rollout type cannot be empty while feature group creation` |
| Faseplan doorgegeven met handmatige tekst | 400 | `Error: PhaseRollOutPlan can't be added with manual rollout type while feature group creation` |
| Tijdschema met GEPUBLICEERDE status | 400 | `Error: Schedule can't be added in published state while release/group creation` |

## Zie ook {#see-also}

* [Overzicht van API&#39;s voor functiebeheer](feature-management-apis-overview.md)
* [API voor kenmerkvlaggen](feature-flags-management-api.md)
* [Beheer van patch-API](management-patch-api.md)
* [Een automatische rollout maken](../guides/automated-rollouts/create-automated-rollout.md)
