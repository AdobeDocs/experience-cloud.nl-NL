---
title: Een functie instellen die geleidelijk moet worden geïmplementeerd
description: Leer hoe u een geleidelijke implementatie op basis van percentages configureert voor een functiemarkering in Adobe Experience Rollouts.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Een functie instellen die geleidelijk moet worden geïmplementeerd {#gradual-rollout-feature}

Het percentage rollout voor een eigenschapvlag wordt gevormd in de **Basis Details** tabel. U kunt deze waarde op elk moment omhoog of omlaag aanpassen terwijl de rollout wordt uitgevoerd.

## Hoe werkt het {#how-it-works}

Wanneer u een percentage voor rollout instelt, bijvoorbeeld 25%, wordt dat percentage van het gedefinieerde publiek aan de functie blootgesteld. Het resterende percentage wordt geplaatst in de **controlegroep**, die de standaardervaring ontvangt.

U kunt het percentage in de loop der tijd verhogen of verlagen om de rollout uit te breiden of in te perken. Als u het percentage tot 0% reduceert, wordt de functie voor iedereen in het publiek uitgeschakeld zonder dat de markering wordt verwijderd.

## Zie ook {#see-also}

* [Geleidelijke rollout](../../concepts/gradual-rollout.md)
* [Een functiegroep instellen die geleidelijk moet worden geïmplementeerd](set-feature-group-gradual-rollout.md)
* [De eerste functiemarkering maken](create-your-first-feature-flag.md)
