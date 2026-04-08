---
title: Context gebruiken in publieksregels
description: Leer hoe u contextvariabelen gebruikt in publieksregels voor functiemarkeringen en functiegroepen in Adobe Experience Rollouts.
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Context gebruiken in publieksregels {#context-in-audience-rules}

Contextvariabelen zijn waarden die door de clienttoepassing bij uitvoering worden verschaft. Hiermee kunt u gebruikers als doel instellen op basis van dynamische informatie op sessieniveau, zoals de actieve taal van de gebruiker, het apparaattype of de toepassingsstatus.

Contextvariabelen zijn relevant voor internet en mobiele clients.

## Werken met contextvariabelen {#how-context-works}

Uw toepassing geeft contextvariabelen aan de Rollouts van de Ervaring door wanneer het evalueren van een eigenschapvlag. U bepaalt regels in de console die deze waarden controleren, en het platform gebruikt hen op het tijdstip van evaluatie om te bepalen of de gebruiker kwalificeert.

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

## Zie ook {#see-also}

* [Publiek in functiemarkeringen en functiegroepen](audience-in-feature-flags-and-feature-groups.md)
* [Percentageregels toevoegen aan publiekscriteria](adding-percentage-rules.md)
