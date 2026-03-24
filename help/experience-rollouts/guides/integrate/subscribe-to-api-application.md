---
title: Abonneren op de API-toepassing in Adobe Developer Console
description: Leer hoe u uw toepassing via Adobe Developer Console abonneert op de Experience Rollouts API, zodat u de eindpunten van de functiemarkering kunt aanroepen.
source-git-commit: 120a2ea34682c878aaf6f6cb75504a8704d10e3d
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---


# Abonneren op de API-toepassing in Adobe Developer Console {#subscribe-to-api}

Om de Rollouts API van de Ervaring van uw toepassing te roepen, moet u aan het door [&#x200B; Adobe Developer Console &#x200B;](https://developer.adobe.com/console) intekenen. Dit geeft uw toepassing een cliëntidentiteitskaart die het gebruik van Rollouts van de Ervaring om de bezoeker te identificeren.

## Vereisten {#prerequisites}

Bevestig het volgende voordat u zich abonneert:

* Uw toepassing wordt in de console van Rollouts van de Ervaring opgenomen — zie [&#x200B; Onboard uw toepassing &#x200B;](../applications/onboard-your-application.md)
* U hebt toegang tot de Adobe Developer Console voor uw organisatie

## Abonneren op de API Experience Rollouts {#subscribe}

Voer de volgende stappen uit om uw toepassing te abonneren op de Experience Rollouts-API:

1. Ga naar [&#x200B; Adobe Developer Console &#x200B;](https://developer.adobe.com/console) en teken binnen met uw organisatiereferenties.
2. Selecteer uw project of maak een nieuw project.
3. Selecteer **toevoegen API**.
4. Onderzoek naar en selecteer **Rollouts API van de Ervaring**.
5. Volg de herinneringen om API te vormen en geloofsbrieven te produceren.
6. Noteer **identiteitskaart van de Cliënt** die voor uw project wordt geproduceerd. Dit is de id die u gebruikt wanneer u de API Experience Rollouts aanroept en wanneer u uw toepassing opneemt in de console Experience Rollouts.

## Server-side SDK-integratie {#server-sdk}

Als u gebruikend Java SDK of Node.js SDK integreert, hebt u a **de dienstteken** cliëntidentiteitskaart naast een API sleutel nodig. Met het servicetoken kan de SDK Experience Rollouts API&#39;s op de achtergrond aanroepen.

>[!NOTE]
>
>Server-side SDK client ID&#39;s moeten worden gevoegd op lijst van gewenste personen door Experience Rollouts-ondersteuning voordat ze API-aanroepen kunnen maken. Neem contact op met de ondersteuning nadat u de Developer Console-instellingen hebt voltooid.

## Zie ook {#see-also}

* [Opstartgids](startup-guide.md)
* [SDK&#39;s](sdks.md)
* [Aan boord van uw toepassing](../applications/onboard-your-application.md)
* [Integratiestappen](integration-steps.md)
