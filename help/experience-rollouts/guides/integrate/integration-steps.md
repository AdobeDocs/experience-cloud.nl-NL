---
title: Integratiestappen
description: Voer de integratiestappen voor uw toepassingstype uit om Adobe Experience Rollouts te verbinden met uw webservice, web- of mobiele app of bureaubladtoepassing.
source-git-commit: b82520eebe0070b5f76e0f7daeb2bb79a4bccca0
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Integratiestappen {#integration-steps}

Kies het integratiepad dat overeenkomt met het toepassingstype.

## Webservices {#web-services}

De diensten van de steun integreren gebruikend server-kant SDK. Kies de SDK voor uw technologiestapel.

**Java**

Volg de [ de integratiegids van SDK van Java ](../sdk-releases/java/java-sdk-integration-guide.md) voor opstelling, gebiedsconfiguratie, en initialisering.

**Node.js**

Volg [ Node.js de integratiegids van SDK ](../sdk-releases/nodejs/nodejs-sdk-integration-guide.md) voor opstelling en initialisering.

**Andere talen**

Als uw stapel hierboven niet vermeld is, integreer direct met de **Eigenschap API V3** (zie de sectie van de Eigenschap API van deze gids). Als u hulp nodig hebt, kunt u contact opnemen met de ondersteuning Rollouts.

## Web- en mobiele toepassingen {#web-mobile}

Het Web en de mobiele toepassingen roepen de **Eigenschap API V3** om eigenschapvlaggen voor de huidige gebruiker terug te winnen en voorwaardelijke logica in de toepassing toe te passen.

Zie **de Eigenschap API van GET V3** in de sectie van de Eigenschap API van deze gids voor de volledige API verwijzing.

## Bureaubladtoepassingen {#desktop}

De toepassingen van de Desktop roepen de **Eigenschap API V2** om eigenschapvlaggen terug te winnen.

Zie **de Eigenschap API van GET V2** in de sectie van de Eigenschap API van deze gids voor de volledige API verwijzing.

>[!IMPORTANT]
>
>Desktopclients moeten de TTL-waarde in de API-reactie respecteren en een foutafhandeling implementeren om de API niet beschikbaar te maken. Zie [ toepassingen van de Desktop ](desktop-applications.md) voor vereisten.

## Zie ook {#see-also}

* [Opstartgids](startup-guide.md)
* [SDK&#39;s](sdks.md)
* [Webservices](web-services.md)
* [Bureaubladtoepassingen](desktop-applications.md)
