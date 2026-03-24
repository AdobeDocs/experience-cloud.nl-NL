---
title: Wat is een functiemarkering
description: Leer welke functiemarkeringen zijn en hoe u toepassingsfuncties tijdens runtime kunt in- of uitschakelen zonder dat u deze opnieuw hoeft te implementeren.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---


# Wat is een functiemarkering {#what-is-a-feature-flag}

Een functiemarkering is een mechanisme waarmee u functies van uw toepassing tijdens runtime kunt in- of uitschakelen, zonder dat u code opnieuw hoeft te implementeren.

De vlaggen van de eigenschap ontkoppelen **codeplaatsing** van **eigenschapbeschikbaarheid**. U kunt nieuwe code naar productie verzenden met de functie verborgen achter een vlag, en deze vervolgens inschakelen wanneer u klaar bent — voor alle gebruikers of voor een doelsubset.

Deze scheiding vermindert het risico aanzienlijk. De ontwikkelaars kunnen en verschepen onophoudelijk met minimale verstoring, terwijl de productteams volledige controle over behouden wanneer en aan wie een eigenschap zichtbaar wordt.

>[!NOTE]
>
>In de Rollouts van de Ervaring, is een eigenschapvlag de meest atomische eenheid van eigenschapcontrole. Het kan op zijn worden gebruikt om één enkele eigenschap, of gecombineerd met andere vlaggen in a [&#x200B; eigenschapgroep &#x200B;](feature-groups-to-control-multiple-features.md) of [&#x200B; versie &#x200B;](release-management.md) te richten.
