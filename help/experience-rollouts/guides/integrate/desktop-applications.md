---
title: Bureaubladtoepassingen
description: Leer hoe u Adobe Experience Rollouts kunt integreren in een bureaubladtoepassing met de functie-API V2.
source-git-commit: b82520eebe0070b5f76e0f7daeb2bb79a4bccca0
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---


# Bureaubladtoepassingen {#desktop-applications}

Desktoptoepassingen integreren met Experience Rollouts door directe REST API-aanroepen te maken. Gebruik de **Eigenschap API V2** voor Desktopcliënten.

Zie **de Eigenschap API van GET V2** in de sectie van de Eigenschap API van deze gids voor de volledige API verwijzing.

## Integratievereisten {#requirements}

Desktopclients moeten:

* **respecteer de waarde van TTL** in de API reactie teruggekeerd. De TTL bepaalt hoe lang de cliënt de gegevens van de eigenschapmarkering zou moeten in het voorgeheugen onderbrengen alvorens API opnieuw te roepen. Voer een testcase uit die dit gedrag valideert om ervoor te zorgen dat oudere versies van de toepassing de slaapstand correct invoeren wanneer er geen functiemarkeringen worden weergegeven.
* **de foutenscenario&#39;s van HTTP van de Behandeling netjes**. Stel een fallback-functie samen die zo is ingesteld dat de toepassing functioneert als de API tijdelijk niet beschikbaar is.
* **handhaaf een gedetailleerd plan van de integratietest** dat zowel van TTL als fout behandelende vereisten hierboven behandelt.

## Toepassings-id {#app-id}

De cliënten van de Desktop kunnen a **productcode en productversie** als toepassingsherkenningsteken gebruiken wanneer het roepen van API, in plaats van een standaardcliëntidentiteitskaart.

## Zie ook {#see-also}

* [Integratiestappen](integration-steps.md)
* [Opstartgids](startup-guide.md)
