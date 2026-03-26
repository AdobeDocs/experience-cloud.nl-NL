---
title: Aan boord van uw toepassing
description: Leer hoe u een nieuwe toepassing instelt op Adobe Experience Rollouts zodat uw team functiemarkeringen kan gaan maken en beheren.
exl-id: d88c27a5-f490-4504-9764-5e4ce98fdf20
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Aan boord van uw toepassing {#onboard-your-application}

U moet de **Admin** rol hebben om een nieuwe toepassing toe te voegen. Neem contact op met uw teambeheerder als u uw rol moet verifiëren of bijwerken.

## Een nieuwe toepassing toevoegen {#add-application}

1. Login aan de console van Rollouts van de Ervaring en navigeer aan **Admin > Toepassingen**.

   >[!NOTE]
   >
   >Als de **Nieuwe knoop van de Toepassing** niet zichtbaar is, verifieer dat u in het correcte team bent en dat u de **Admin** rol hebt.

2. Selecteer **Nieuwe Toepassing**.

3. Selecteer het **kanaal** dat uw toepassingstype (Web, mobiel, Desktop, of de dienst) aanpast.

4. Geef de volgende informatie op:

   | Veld | Beschrijving |
   |---|---|
   | **identiteitskaart van de Toepassing** | Een unieke id die wordt gebruikt wanneer u Experience Rollouts aanroept vanuit uw code. Gebruik de client-id van uw toepassing. |
   | **TTL** | Het opiniepeilingsinterval (in seconden) voor het vernieuwen van de cache per toepassing. Is alleen van toepassing op SDK&#39;s aan de serverzijde. |
   | **Team** | Het team dat eigenaar is van deze toepassing en deze zal beheren. Alleen leden van dit team kunnen functiemarkeringen maken en bewerken. |

5. Selecteer **toevoegen**. Uw toepassing is nu geregistreerd en klaar voor configuratie van de eigenschapmarkering.

## Wat volgt {#next-steps}

Zodra uw toepassing wordt geregistreerd, kan uw team beginnen eigenschapmarkeringen tot stand te brengen:

* [De eerste functiemarkering maken](../feature-flags/create-your-first-feature-flag.md)
* [Integreer Experience Rollouts in uw app](../integrate/integrating-in-your-app.md)

## Zie ook {#see-also}

* [Toepassingen beheren](manage-applications.md)
* [Aanmelden bij de console](../console/log-in-to-the-console.md)
