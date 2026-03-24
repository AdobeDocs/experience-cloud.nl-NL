---
title: Context gebruiken in publieksregels
description: Leer hoe u contextvariabelen gebruikt in publieksregels voor functiemarkeringen en functiegroepen in Adobe Experience Rollouts.
source-git-commit: 3f3f7145b3c58dc721cbeb850e9e8571e3255bb1
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---


# Context gebruiken in publieksregels {#context-in-audience-rules}

Contextvariabelen zijn waarden die door de clienttoepassing bij uitvoering worden verschaft. Hiermee kunt u gebruikers als doel instellen op basis van dynamische informatie op sessieniveau, zoals de actieve taal van de gebruiker, het apparaattype of de toepassingsstatus — criteria die geen deel uitmaken van het permanente profiel van de gebruiker.

Contextvariabelen zijn relevant voor webclients, desktops en mobiele clients.

## Werken met contextvariabelen {#how-context-works}

Uw toepassing geeft contextvariabelen aan de Rollouts van de Ervaring door wanneer het evalueren van een eigenschapvlag. U bepaalt regels in de console die deze waarden controleren, en het platform gebruikt hen op het tijdstip van evaluatie om te bepalen of de gebruiker kwalificeert.

Als u voorwaarden in zowel het **Profiel** als **Context** secties van de publieksregels bepaalt, worden alle profielvoorwaarden gecombineerd met alle contextvoorwaarden gebruikend EN logica.

## Typen contextvariabelen {#variable-types}

### Type vooraf gedefinieerd (lijst) {#predefined-type}

Een contextvariabele met een vaste set toegestane waarden, zoals een lijst met talen of landen.

Beschikbare exploitanten: **is**, **is niet gelijk aan**, **bestaat**, **binnen**

### Het type Integer {#integer-type}

Een contextvariabele die een numerieke waarde bevat.

Beschikbare exploitanten: **Groter dan**, **Groter dan of gelijk aan**, **is**, **minder dan**, **minder dan of gelijk aan**

### Het type String {#string-type}

Een contextvariabele die een vrije tekstwaarde bevat.

Beschikbare exploitanten: **is**, **is niet gelijk aan**

## Een contextvariabele toevoegen {#adding-context-variable}

Een contextvariabele toevoegen aan een publieksregel:

1. Open de eigenschapvlag of eigenschapgroep in de console.
2. Ga naar het **publiek** lusje.
3. Onder **Context**, voeg een nieuwe voorwaarde toe.
4. Selecteer de contextvariabele, operator en waarde.

Als de contextvariabele u nodig niet in de lijst verschijnt, kunt u nieuwe op een zelf-bediende manier van de sectie van het de contextveranderlijke beheer van de console creëren.

>[!NOTE]
>
>Wanneer de contextvariabelen in publiekscriteria inbegrepen zijn, keert de **Rekenmachine van het Publiek** geen geschatte telling terug, omdat de contextwaarden bij runtime worden bepaald en niet vooraf kunnen worden voorspeld.

## Zie ook {#see-also}

* [Publiek in functiemarkeringen en functiegroepen](audience-in-feature-flags-and-feature-groups.md)
* [Percentageregels toevoegen aan publiekscriteria](adding-percentage-rules.md)
* [De regel van het publiek met cliëntIP contextvariabele](clientip-rule.md)
