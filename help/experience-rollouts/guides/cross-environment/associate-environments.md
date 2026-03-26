---
title: Omgevingen koppelen aan een toepassing
description: Leer hoe u toepassingsinstanties in verschillende omgevingen in Adobe Experience Rollouts kunt koppelen, zodat u functiemarkeringen consistent kunt beheren, van ontwikkeling tot productie.
exl-id: 53080db1-f257-4369-82ab-57c84395a40a
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Omgevingen koppelen aan een toepassing {#associate-environments}

Door de toepassingsinstanties aan elkaar te koppelen in verschillende omgevingen, kunt u de zichtbaarheid van verschillende omgevingen verhogen en workflows importeren. U moet de **Admin** rol hebben om dit te vormen. Neem contact op met uw teambeheerder als u uw rol moet verifiëren of bijwerken.

Voor achtergrond waarom dit nuttig is, zie [ Cross-environment concept ](cross-environment-concept.md).

## Stap 1: De toepassingsinstellingen openen {#step-1}

1. Meld u aan bij de Experience Rollouts-console.
2. Navigeer aan **Admin > Toepassingen**.
3. Selecteer **Nieuwe Toepassing** aan boord een nieuwe app, of selecteer een bestaande toepassing om het uit te geven.

## Stap 2: De sectie Gekoppelde omgevingen configureren {#step-2}

In de toepassingsvorm, rol aan de **Verwante sectie van Milieu&#39;s**. Elke rij in deze sectie definieert een van de implementatieomgevingen van uw toepassing. Configureer voor elke omgeving de volgende velden:

| Veld | Beschrijving |
|---|---|
| **Milieu** | Selecteer een standaardomgevmilieu-id van de lijst: QA1, QA2, STG1, STG2, PROD1, of PROD2. Dit vertelt Rollouts van de Ervaring of het milieu productie of niet-productie is, en bepaalt de kleurencodering die in de console wordt gebruikt. |
| **etiket van het Milieu** | Een aangepaste naam voor deze omgeving zoals uw team ernaar verwijst, bijvoorbeeld `Dev` , `Staging` of `Production` . Dit is een vrije vorm en hoeft niet overeen te komen met de standaard-id. |
| **het milieu van Rollouts van de Ervaring** | De platformomgeving (werkgebied of productie) waarin deze toepassingsinstantie wordt gehost. Vooraf ingevuld op basis van de console waarin u zich momenteel bevindt. |
| **identiteitskaart van de Toepassing** | De client-id van de toepassingsinstantie in deze omgeving. Deze optie wordt automatisch ingevuld wanneer u een toepassing selecteert in het keuzemenu. |

## Stap 3: De toepassingsinstanties van de verbinding over milieu&#39;s {#step-3}

Om instanties over milieu&#39;s te verbinden, volg deze stappen voor elke extra milieu:

1. Maak de toepassingsinstantie in de doelomgeving (maak bijvoorbeeld de QA-toepassing in de Stage-console).
2. Terugkeer aan de toepassing u vormt en voegt een nieuwe rij in **Verwante Milieu&#39;s** toe.
3. Van **identiteitskaart van de Toepassing** drop-down, selecteer de toepassingsinstantie u enkel creeerde. De omgevingscode en het label worden automatisch ingevuld.
4. Selecteer **Update** om te bewaren.

Herhaal dit proces voor elke omgeving die u wilt koppelen, bijvoorbeeld het koppelen van instanties van QA, Stage en Production van dezelfde toepassing.

## Belangrijke opmerkingen {#important-notes}

* De milieu&#39;s van QA en van het Stadium kunnen in of het Stadium van de Rollouts van de Ervaring of het milieu van het platform van de Productie worden ontvangen.
* Productieomgevingen (PROD1, PROD2) kunnen alleen worden gehost in de Experience Rollouts Production-omgeving.
* U kunt alleen vanuit een hogere omgeving koppelen aan een lagere omgeving. Vanuit Production kunt u bijvoorbeeld een koppeling maken naar een Stage- of QA-instantie, maar het omgekeerde is alleen-lezen.

## Zie ook {#see-also}

* [Concept tussen milieu en milieu](cross-environment-concept.md)
* [Functievlaggen weergeven in verschillende omgevingen](view-feature-flags-across-environments.md)
* [Markeringen voor importfuncties](import-feature-flags.md)
