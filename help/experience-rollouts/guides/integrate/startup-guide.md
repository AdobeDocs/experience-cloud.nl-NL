---
title: Opstartgids
description: Voer de volgende stappen uit om uw toepassing te integreren met Adobe Experience Rollouts, van het aanvragen van toegang tot het maken van uw eerste functiemarkering.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---


# Opstartgids {#startup-guide}

Ga als volgt te werk om Experience Rollouts in uw toepassing te integreren.

## Stap 1: Toegang aanvragen {#step-1-access}

Vraag om toegang tot de console van de Rollouts van de Ervaring en sluit zich bij uw team aan. Zie [&#x200B; toegang van het Verzoek &#x200B;](../console/request-access.md) voor geleidelijke instructies.

## Stap 2: Aan boord van uw toepassing {#step-2-onboard}

Nadat u toegang hebt gekregen, meldt u zich aan bij de console Experience Rollouts en controleert u of uw toepassing onder uw team wordt vermeld. Als dat niet het geval is, vraagt u de teambeheerder om het toe te voegen. Zie [&#x200B; aan boord uw toepassing &#x200B;](../applications/onboard-your-application.md).

Bereid het volgende voor voordat u aan boord gaat:

| Vereiste | Details |
|---|---|
| **identiteitskaart van de Toepassing** | Een unieke client-id die wordt gebruikt bij het aanroepen van de API&#39;s van Experience Rollouts. Gebruik de bestaande client-id van uw toepassing, indien beschikbaar. |
| **server-zij cliënten** | Als u wilt integreren met een SDK aan de serverzijde, hebt u een client-id voor beheerders met de juiste machtigingen nodig. |
| **cliënten van de Desktop** | U kunt een productcode en een productversie gebruiken in plaats van een client-id. |

## Stap 3: Abonneren op de API Experience Rollouts {#step-3-subscribe}

Schrijf u in via de Adobe Developer Console in op de API Experience Rollouts, zodat uw toepassing de eindpunten van de functiemarkering kan aanroepen. Zie [&#x200B; aan de API toepassing in Adobe Developer Console &#x200B;](subscribe-to-api-application.md) intekenen.

>[!NOTE]
>
>Als u integreert via een server-side SDK, hebt u een client-id voor het servicetoken nodig. De steun van Rollouts van de Ervaring van het contact om uw cliëntidentiteitskaart te laten gevoegd op lijst van gewenste personen.

## Stap 4: Integreer met een SDK of de API {#step-4-integrate}

Volg de [&#x200B; integratiestappen &#x200B;](integration-steps.md) voor uw toepassingstype. Kies het pad dat bij de stapel past:

* **de diensten van het Web** → Java SDK of Node.js SDK
* **Web en mobiele apps** → Eigenschap API V3
* **Desktop apps** → Eigenschap API V2

## Stap 5: Maak en test de eerste functiemarkering {#step-5-feature-flag}

Zodra de integratie volledig is, creeer uw eerste eigenschapvlag in de console en test het:

* [De eerste functiemarkering maken](../feature-flags/create-your-first-feature-flag.md)

## Zie ook {#see-also}

* [Integreer Experience Rollouts in uw app](integrating-in-your-app.md)
* [Integratiestappen](integration-steps.md)
* [SDK&#39;s](sdks.md)
