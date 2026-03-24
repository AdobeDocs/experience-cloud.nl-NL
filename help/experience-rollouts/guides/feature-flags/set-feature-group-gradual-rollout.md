---
title: Een functiegroep instellen die geleidelijk moet worden geïmplementeerd
description: Leer hoe u een geleidelijke implementatie op basis van percentages configureert voor een functiegroep in Adobe Experience Rollouts.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Een functiegroep instellen die geleidelijk moet worden geïmplementeerd {#gradual-rollout-feature-group}

Het percentage rollout voor een eigenschapgroep wordt gevormd in de **Basis Details** tabel. U kunt deze waarde op elk moment omhoog of omlaag aanpassen terwijl de rollout wordt uitgevoerd.

## Hoe werkt het {#how-it-works}

Wanneer u een percentage van uitrol - bijvoorbeeld, 60% - plaatst dat percentage van uw bepaalde publiek wordt blootgesteld aan de eigenschapgroep. De resterende 40% wordt geplaatst in de **controlegroep**, die standaardgedrag ontvangt.

Als u meerdere varianten hebt geconfigureerd (voor A/B-tests), wordt het belichtingspercentage gelijkmatig over de varianten verdeeld. 60% blootstelling met drie varianten resulteert bijvoorbeeld in 20% per variant, met 40% in de controlegroep.

U kunt het percentage op elk gewenst moment verhogen of verlagen om de rollout uit te breiden, te verkleinen of te pauzeren.

## Zie ook {#see-also}

* [Een functiegroep maken](create-a-feature-group.md)
* [A/B testen met functiemarkeringen](a-b-testing.md)
* [Geleidelijke rollout](../../concepts/gradual-rollout.md)
