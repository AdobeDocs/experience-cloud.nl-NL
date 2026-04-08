---
title: Wat is een functiemarkering
description: Leer welke functiemarkeringen zijn en hoe u toepassingsfuncties tijdens runtime kunt in- of uitschakelen zonder dat u deze opnieuw hoeft te implementeren.
exl-id: c4ed4ab5-0d73-4697-b05c-476d6e4010ce
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Wat is een functiemarkering {#what-is-a-feature-flag}

Een functiemarkering is een mechanisme waarmee u functies van uw toepassing tijdens runtime kunt in- of uitschakelen, zonder dat u code opnieuw hoeft te implementeren.

De vlaggen van de eigenschap ontkoppelen **codeplaatsing** van **eigenschapbeschikbaarheid**. U kunt nieuwe code naar productie verzenden met de functie verborgen achter een vlag, en deze vervolgens inschakelen wanneer u klaar bent — voor alle gebruikers of voor een doelsubset.

Deze scheiding vermindert het risico aanzienlijk. De ontwikkelaars kunnen en verschepen onophoudelijk met minimale verstoring, terwijl de productteams volledige controle over behouden wanneer en aan wie een eigenschap zichtbaar wordt.

>[!NOTE]
>
>In de Rollouts van de Ervaring, is een eigenschapvlag de meest atomische eenheid van eigenschapcontrole. Het kan op zijn worden gebruikt om één enkele eigenschap, of gecombineerd met andere vlaggen in a [ eigenschapgroep ](feature-groups-to-control-multiple-features.md) te richten.
