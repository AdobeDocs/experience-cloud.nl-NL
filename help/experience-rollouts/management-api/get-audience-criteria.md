---
title: Kies de gewenste publiekscriteria
description: Leer hoe u de juiste JSON-publiekscriteria genereert voor gebruik in de API's voor het beheer van Experience Rollouts met de console en de GET-functie-API.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---


# Kies de gewenste publiekscriteria {#get-audience-criteria}

Het veld voor publiekscriteria in de beheer-API&#39;s gebruikt een gestructureerde JSON-indeling die handmatig kan worden geschreven. De geadviseerde benadering is het gewenste publiek te bouwen gebruikend de console en dan zijn vertegenwoordiging JSON via API terug te winnen.

## Stappen {#steps}

Ga als volgt te werk om de JSON voor een gewenst publiek te verkrijgen:

1. In de console van Rollouts van de Ervaring, creeer een tijdelijke eigenschapvlag met de publiekscriteria u in uw API vraag wilt gebruiken.
2. Noteer na het opslaan de markering-id van de functie in de URL van de browser. De id wordt na de client-id in de URL weergegeven. In `.../feature-flags/1191/22080` is de functie-id bijvoorbeeld `22080` .
3. Vraag [ krijgt Eigenschap door identiteitskaart ](feature-flags-management-api.md#get-feature-by-id) eindpunt met die eigenschapidentiteitskaart
4. Zoek in het antwoord-JSON het veld `audience` . Dit bevat de exacte publiekscriteria-structuur die u nodig hebt.
5. Kopieer de waarde `audience` en verwijder het kenmerk `id` uit elk regelobject. Gebruik dit in de aanroep van de functie-API voor maken of bijwerken.

## Voorbeeld {#example}

Na het aanroepen van GET `/m/api/v1/mgmt/feature/22080` omvat de reactie:

```json
{
  "audience": [
    {
      "id": 10034665,
      "criteria": {
        "and": [
          {
            "operator": "EQ",
            "attr": "LOCALE",
            "val": "EN",
            "ruleId": 1,
            "category": "default"
          }
        ]
      }
    }
  ]
}
```

Als u dit wilt gebruiken in een aanroep van de functie Maken, verwijdert u het veld `id` uit het publieksobject:

```json
{
  "audience": [
    {
      "criteria": {
        "and": [
          {
            "operator": "EQ",
            "attr": "LOCALE",
            "val": "EN",
            "ruleId": 1,
            "category": "default"
          }
        ]
      }
    }
  ]
}
```

## Zie ook {#see-also}

* [API voor kenmerkvlaggen](feature-flags-management-api.md)
* [Client-id voor een toepassing ophalen](get-client-id.md)
* [Beheer van patch-API](management-patch-api.md)
