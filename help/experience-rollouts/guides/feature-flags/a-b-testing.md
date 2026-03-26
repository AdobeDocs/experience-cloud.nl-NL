---
title: A/B testen met functiemarkeringen
description: Leer hoe te om tests A/B in werking te stellen gebruikend eigenschapgroepen in de Rollouts van de Ervaring van Adobe door veelvoudige varianten voor een reeks eigenschapmarkeringen te vormen.
exl-id: bb849049-229c-40ff-bbfe-7996f868bcc3
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# A/B testen met functiemarkeringen {#a-b-testing}

A/B de tests in de Rollouts van de Ervaring worden uitgevoerd gebruikend **eigenschapgroepen**. Door meer dan één variant in een eigenschapgroep te vormen, kunt u verschillende versies van een eigenschap aan verschillende ondergroepen van uw publiek dienen en resultaten vergelijken.

## Vereisten {#prerequisites}

* U hebt toegang tot de console — zie [&#x200B; Login aan de console &#x200B;](../console/log-in-to-the-console.md)
* U maakt deel uit van een team en uw toepassing is aan boord
* U hebt de **rol van de Eigenaar van de Versie van de Ontwikkelaar** of **Product**
* U hebt de eigenschapvlaggen gecreeerd om te testen — zie [&#x200B; uw eerste eigenschapvlag &#x200B;](create-your-first-feature-flag.md) creëren

## Stap 1: Maak een functiegroep met meerdere varianten {#create}

1. Navigeer aan **het Testen van de Eigenschap > de Groepen van de Eigenschap** en selecteer **Nieuwe Groep van de Eigenschap**.
2. In **Basisdetails**, verstrek een titel, een sleutel, en een beschrijving.
3. Plaats a **percentenuitrol** om te bepalen hoeveel van uw publiek aan de test deelneemt.
4. Plaats **Varianten** aan een waarde groter dan één (bijvoorbeeld, twee varianten voor een klassieke A/B test).
5. Zie [&#x200B; plaats een eigenschapgroep om uit geleidelijk te rollen &#x200B;](set-feature-group-gradual-rollout.md) om te begrijpen hoe het blootstellingspercentage over varianten wordt verdeeld.

## Stap 2: Het publiek instellen {#audience}

Voor het **publiek** lusje, voeg publiekscriteria toe en selecteer de toepassingen om te omvatten. De groepen van de eigenschap kunnen veelvoudige toepassingen binnen het zelfde team omvatten.

>[!NOTE]
>
>Om externe gebruikers in een test van A/B te richten, moet u de **rol van de Eigenaar van de Versie van het 0&rbrace; Product hebben.** De rol van de Ontwikkelaar is sandbox en beperkt zich tot privé testen.

## Stap 3: functies toevoegen per variant {#features}

Onder het **lusje van Eigenschappen**, heeft elke variant zijn eigen lusje. Voeg de aangewezen eigenschapmarkeringen aan elke variant toe om de verschillende ervaringen te bepalen u wilt vergelijken.

>[!IMPORTANT]
>
>Een eigenschapvlag kan slechts door één methode tegelijkertijd worden gediend — eigenschapvlag, eigenschapgroep, of versie. Als u een vlag toevoegt aan een functiegroep, worden alle doelgroepen of percentages verwijderd die rechtstreeks op de markering zijn ingesteld.

## Stap 4: Opslaan en activeren {#save}

Sla de instellingen van de functiegroep op. Wanneer u klaar bent om de test te beginnen, plaats de eigenschapgroep aan de actieve staat.

## Zie ook {#see-also}

* [Een functiegroep maken](create-a-feature-group.md)
* [Een functiegroep instellen die geleidelijk moet worden geïmplementeerd](set-feature-group-gradual-rollout.md)
* [Analyse](analytics.md)
