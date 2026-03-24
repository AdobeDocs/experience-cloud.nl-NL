---
title: Beheer van patch-API
description: Met de Experience Rollouts PATCH API kunt u afzonderlijke velden van een functiemarkering, functiegroep of functiegroep die zich uitstrekken over een team bijwerken zonder het volledige object door te geven.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---


# Beheer van patch-API {#management-patch-api}

Met de PATCH API kunt u specifieke velden van een functiemarkering, functiegroep of functiegroep die betrekking heeft op meerdere teams bijwerken zonder het volledige object in de aanvraaginstantie te verzenden. Dit is nuttig voor gerichte updates zoals het veranderen van een publieksregel, het van een knevelstaat, of het aanpassen van een variatiepercentage.

## Functiemarkering PATCH {#feature-flag-patch}

Werkt een of meer velden van een functiemarkering bij.

| | |
|---|---|
| **Eindpunt** | `PATCH /m/api/v1/mgmt/feature/{featureFlagId}` |
| **Methode** | PATCH |

### Aanvraagkoppen {#ff-request-headers}

Alle verzoeken vereisen de kopballen die in de [&#x200B; worden beschreven gemeenschappelijke vereisten &#x200B;](feature-management-apis-overview.md#common-requirements).

### Padparameter {#ff-path-param}

| Parameter | Type | Beschrijving | Vereist |
|---|---|---|---|
| `featureFlagId` | Geheel | De numerieke id van de functiemarkering die moet worden bijgewerkt. | Ja |

### Aanvragingsinstantie {#ff-request-body}

Geef alleen de velden door die u wilt bijwerken. De reactie retourneert altijd het volledige bijgewerkte object feature-markering.

**Voorbeeld — update slechts beschrijving:**

```json
{
  "description": "Updated description"
}
```

**Voorbeeld — verwijder bestaand publiek:**

```json
{
  "audience": null
}
```

**Voorbeeld — voeg een nieuw publiek toe wanneer niets bestond:**

```json
{
  "audience": [
    {
      "criteria": {
        "and": [
          { "operator": "EQ", "attr": "sandboxType", "val": "DEVELOPMENT", "ruleId": 1, "category": "contextual" }
        ]
      }
    }
  ]
}
```

**Voorbeeld — werk een bestaande publieksregel bij:**

```json
{
  "audience": [
    {
      "id": 10020035,
      "criteria": {
        "and": [
          { "operator": "EQ", "attr": "sandboxType", "val": "PRODUCTION", "ruleId": 1, "category": "contextual" }
        ]
      }
    }
  ]
}
```

**Voorbeeld — veranderingsstaat en variatiepercentage:**

```json
{
  "state": "disabled",
  "variations": [
    {
      "id": 10017188,
      "variantName": "Variation 1",
      "variantPercentage": 80.0
    }
  ]
}
```

>[!NOTE]
>
>Wanneer u een bestaande publieksregel bijwerkt, neemt u de `id` -regel (beschikbaar in de GET-functiereactie) op om deze op zijn plaats bij te werken. Wanneer u variaties bijwerkt, neemt u de variatie `id` op om te voorkomen dat er een duplicaat wordt gemaakt.

### Antwoord {#ff-response}

| Status | Beschrijving |
|---|---|
| `200` | Geslaagd. De hoofdtekst van de reactie is het volledige bijgewerkte voorwerp van de eigenschapmarkering. |
| `400` | Ongeldige lading. |
| `403` | Onvoldoende machtigingen. |
| `417` | Conflict tussen gelijktijdige updates. Haal de huidige functie op en probeer het opnieuw. |

## Functiegroep PATCH {#feature-group-patch}

Hiermee werkt u een of meer velden van een functiegroep bij. De verzoek- en reactiestructuur zijn hetzelfde als de eigenschapmarkering PATCH — alleen het eindpunt verschilt.

| | |
|---|---|
| **Eindpunt** | `PATCH /m/api/v1/mgmt/group/{featureGroupId}` |
| **Methode** | PATCH |

## Groep met functies voor verschillende teams PATCH {#ctfg-patch}

Werkt één of meerdere gebieden van een dwars-teameigenschapgroep bij. Gebruikt het v2 versieeindpunt.

| | |
|---|---|
| **Eindpunt** | `PATCH /m/api/v2/mgmt/release/{CTFGId}` |
| **Methode** | PATCH |

## Zie ook {#see-also}

* [API voor kenmerkvlaggen](feature-flags-management-api.md)
* [API voor beheer van functiegroepen](feature-group-management-api.md)
* [Beheer-API&#39;s vrijgeven](release-management-apis.md)
* [Overzicht van API&#39;s voor functiebeheer](feature-management-apis-overview.md)
