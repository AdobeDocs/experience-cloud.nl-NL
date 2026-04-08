---
title: Aan boord van uw toepassing
description: Leer hoe u een nieuwe toepassing kunt opnemen in Adobe Experience Rollouts, zodat u functiemarkeringen kunt maken en beheren.
exl-id: d88c27a5-f490-4504-9764-5e4ce98fdf20
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# Aan boord van uw toepassing {#onboard-your-application}

U moet de **Admin** rol hebben om een nieuwe toepassing toe te voegen. Neem contact op met uw beheerder als u uw rol moet verifiëren of bijwerken.

## Een nieuwe toepassing toevoegen {#add-application}

1. Login aan de console van Rollouts van de Ervaring en navigeer aan **Uitvoer van de Ervaring > Toepassingen**.

   >[!NOTE]
   >
   >Als de **Nieuwe knoop van de Toepassing** niet zichtbaar is, verifieer dat u de **rol Admin van de Vullinggate** hebt.

2. Selecteer **Nieuwe Toepassing**.

3. Selecteer het **platform** dat uw toepassingstype (Web of mobiel) aanpast.

4. Geef de volgende informatie op:

   | Veld | Beschrijving |
   |---|---|
   | **identiteitskaart van de Toepassing** | Een unieke id die wordt gebruikt wanneer u Experience Rollouts aanroept vanuit uw code. Gebruik de client-id van uw toepassing. |
   | **TTL** | Het opiniepeilingsinterval (in seconden) voor het vernieuwen van de cache per toepassing. Is alleen van toepassing op SDK&#39;s aan de serverzijde. |

5. Selecteer **toevoegen**. Uw toepassing is nu geregistreerd en klaar voor configuratie van de eigenschapmarkering.

## Wat volgt {#next-steps}

Wanneer uw toepassing is gestart, kunt u functiemarkeringen maken:

* [De eerste functiemarkering maken](../feature-flags/create-your-first-feature-flag.md)
* [Integreer Experience Rollouts in uw app](../integrate/integrating-in-your-app.md)

## Zie ook {#see-also}

* [Toepassingen beheren](manage-applications.md)
* [Aanmelden bij de console](../console/log-in-to-the-console.md)
