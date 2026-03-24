---
title: Client-id voor een toepassing ophalen
description: Leer hoe u de numerieke client-id voor een toepassing kunt vinden in de Experience Rollouts-console, die vereist is wanneer u de beheer-API's oproept.
source-git-commit: 6ecedbfc6c7de392f214f3f8f2e71aa18e1bacb9
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---


# Client-id voor een toepassing ophalen {#get-client-id}

De functiemarkeringen en API&#39;s voor functiegroepen vereisen een numerieke `clientId` om te bepalen tot welke toepassing de functie behoort. Dit is anders dan de op tekenreeks gebaseerde IMS client-id die wordt gebruikt voor API-verificatie.

Voer de volgende stappen uit om de numerieke client-id voor een toepassing te zoeken.

## Stappen {#steps}

Ga als volgt te werk om de numerieke client-id voor een toepassing te zoeken:

1. Meld u aan bij de Experience Rollouts-console.
2. Navigeer aan **Eigenschappen &amp; Versies**.
3. Selecteer de **Vlaggen van de Eigenschap** tabel.
4. Open **drop-down van de Toepassing** en selecteer de toepassing waarvan cliëntidentiteitskaart u nodig hebt.
5. Kijk naar de URL in de adresbalk van uw browser. Na `feature-flags/` wordt de numerieke client-id voor die toepassing weergegeven.

Als de URL bijvoorbeeld eindigt met `.../feature-flags/1191/...` , is de client-id `1191` .

## De client-id gebruiken in API-aanroepen {#use-in-api}

Geef deze waarde door als de parameter `clientId` in API-aanvragen voor beheer. Wanneer u bijvoorbeeld een functiemarkering maakt:

```json
{
  "name": "my-feature-flag",
  "clientId": 1191,
  "state": "disabled"
}
```

## Zie ook {#see-also}

* [API voor kenmerkvlaggen](feature-flags-management-api.md)
* [API voor beheer van functiegroepen](feature-group-management-api.md)
* [Kies de gewenste publiekscriteria](get-audience-criteria.md)
