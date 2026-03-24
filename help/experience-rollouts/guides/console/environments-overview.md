---
title: Overzicht van omgevingen
description: Leer over het Stadium en de milieu's van de Productie in Adobe Ervaring Rollouts en wanneer om elk te gebruiken.
source-git-commit: 9bfe0e55e89c1d7fbd77cde63831a6a186820e24
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 1%

---


# Overzicht van omgevingen {#environments}

Experience Rollouts biedt verschillende omgevingen, zodat u de functiemarkeringen kunt valideren voordat u wijzigingen aan uw live gebruikers kunt doorvoeren.

## Beschikbare omgevingen {#available-environments}

| Omgeving | Doel |
|---|---|
| **Stadium** | Testen en valideren. Gebruik dit milieu om eigenschapmarkeringen te vormen en te testen alvorens hen in Productie toe te laten. |
| **Productie** | Live rollouts. De vlaggen van de eigenschap die hier worden gevormd worden geëvalueerd tegen uw echte gebruikersbasis. |

>[!IMPORTANT]
>
>Wijzigingen in het werkgebied worden niet automatisch doorgevoerd in Productie. De vlaggen van de eigenschap en de publieksregels moeten afzonderlijk in elk milieu worden gevormd.

## Een omgeving selecteren {#selecting}

Na het programma openen aan de console van Rollouts van de Ervaring, selecteer het milieu van milieuschakelaar bij de bovenkant van de interface. Zorg ervoor dat u in de juiste omgeving werkt voordat u functiemarkeringen maakt of wijzigt.

## Aanbevolen procedures {#best-practices}

Volg deze aanbevelingen om configuratiefouten te vermijden en uw productiepubliek te beschermen:

* Creëer en test de eigenschapvlaggen altijd eerst in **Stadium**.
* Valideer publieksregels, percentage rollouts en logica voor doelframes in het werkgebied voordat u deze repliceert in Production.
* Gebruik het [&#x200B; dwars-milieu werkschema &#x200B;](../cross-environment/cross-environment-concept.md) om vlagstatus over milieu&#39;s te bekijken en te beheren.

## Zie ook {#see-also}

* [Aanmelden bij de console](log-in-to-the-console.md)
* [Omgevingen koppelen aan een toepassing](../cross-environment/associate-environments.md)
* [Functievlaggen weergeven in verschillende omgevingen](../cross-environment/view-feature-flags-across-environments.md)
