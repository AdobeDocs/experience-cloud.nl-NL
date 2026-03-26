---
title: Enterprise-org-gegevens gebruiken in publieksregels
description: Leer hoe u id's van bedrijfsorganisaties als publiekscriteria in Adobe Experience Rollouts kunt gebruiken om specifieke klantenorganisaties te richten.
exl-id: 74f97ec7-a809-41bf-a41d-bb57f033040f
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Enterprise-org-gegevens gebruiken in publieksregels {#enterprise-org-data}

Experience Rollouts biedt ondersteuning voor gebruikers die zich richten op hun bedrijfs-organisatie (org)-id. Dit staat u toe om eigenschappen aan specifieke klantenorganisaties uit te rollen alvorens hen globaal ter beschikking te stellen.

## Een org toevoegen aan een publieksregel {#adding-org-rule}

Het richten van de onderneming is beschikbaar op het **lusje van het publiek** onder **Regels van het publiek > Profiel > Onderneming**.

Er worden twee org-typen ondersteund:

### DME orgs {#dme-orgs}

DME-organen worden geïdentificeerd door hun org-id. Wanneer u de regel maakt, voert u alleen de org-id in. Gebruik geen autebron.

### DMA orgs {#dma-orgs}

DMA-organisaties gebruiken org-id&#39;s in de notatie `XXXXXXXXXXXXXXXXXXXXXXXX@ADOBEORG` . Bij het invoeren van een DMA org-id:

* Gebruik de volledige org-id inclusief het achtervoegsel `@ADOBEORG` .
* Voer `ADOBEORG` in alle hoofdletters in.

**Voorbeeld:** `57F22B5D5A5F83AE0A495E6E@ADOBEORG`

## Belangrijke opmerkingen {#important-notes}

* Het op volgorde-gebaseerde richten wordt geëvalueerd tegen de organisatie verbonden aan de voor authentiek verklaarde zitting van de gebruiker. Zorg ervoor dat de gebruiker zich bij het testen bij de juiste organisatie heeft aangemeld.
* Als een org u verwacht te vinden niet in de publiekscriteria verschijnt, of als de eigenschappen niet zoals die voor een specifieke org worden verwacht, de steun van Rollouts van de Ervaring worden teruggegeven.
* Werkgebied- en productieomgevingen kunnen verschillen in de beschikbare organismen. Test de publieksregels in het werkgebied voordat u een upgrade naar Productie uitvoert.

## Zie ook {#see-also}

* [Publiek in functiemarkeringen en functiegroepen](audience-in-feature-flags-and-feature-groups.md)
* [Complexe publieksregels](complex-rules.md)
