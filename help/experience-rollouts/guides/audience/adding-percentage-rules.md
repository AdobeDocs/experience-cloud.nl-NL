---
title: Percentageregels toevoegen aan publiekscriteria
description: Leer hoe u op percentage-gebaseerde regels binnen publiekscriteria in de Rollouts van de Ervaring van Adobe toevoegt om verschillende rollout percentages voor verschillende publiekssegmenten te richten.
exl-id: 15a3c26f-31fc-4e73-aa0e-035dcbe7d770
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# Percentageregels toevoegen aan publiekscriteria {#adding-percentage-rules}

## Wanneer moet u percentageregels gebruiken op het tabblad publiek {#when-to-use}

Het **gebied van de procentuele uitrol** op het Basis lusje van Details past één enkel percentage op uw volledig publiek toe. 50% rollout betekent bijvoorbeeld dat 50% van alle gebruikers die voldoen aan de criteria voor uw doelgroep de functie ontvangen.

Sommige rollout-scenario&#39;s vereisen echter verschillende percentages voor verschillende groepen, bijvoorbeeld:

* 100% van de Britse gebruikers en 50% van de Amerikaanse gebruikers
* Alle gebruikers uit een geïmporteerde e-maillijst plus 50% van de gebruikers uit een bepaald land

In deze gevallen, gebruik de **regel van het Percentage** in de **de contextsectie van het publiek** lusje van het publiek, gecombineerd met genestelde logica.

>[!TIP]
>
>Als u één enkel percentage over uw volledig publiek wilt toepassen — bijvoorbeeld, 10% van gebruikers in (V.S. en VK) — gebruik in plaats daarvan de **percentenuitloop** op het Basis lusje van Details.

## Een percentageregel toevoegen {#how-to-add}

De **optie van het Percentage** is beschikbaar als regel in de contextsectie van het Publiek tabel.

1. Ga naar het **publiek** lusje van uw eigenschapvlag of eigenschapgroep.
2. Onder **Publiek**, voeg de regel van het Percentage van de a **Context** toe en plaats de gewenste waarde.
3. Voeg andere publieksvoorwaarden toe die u nodig hebt (bijvoorbeeld een landregel).

## Het combineren van percentageregels met geneste logica {#nested-logic}

Om verschillende percentages op verschillende segmenten toe te passen, gebruik **genestelde logica** om de voorwaarden te combineren:

1. Laat **Genestelde Logiek** in de sectie van de publieksregels toe.
2. Aan elke voorwaarde wordt automatisch een nummer toegewezen.
3. Voer een logische expressie in die naar die getallen verwijst.

Gebruik een van de volgende expressies om de relatie tussen uw voorwaarden te beschrijven:

* `1 and (2 or 3)` — voorwaarde 1 EN (voorwaarde 2 OF voorwaarde 3)
* `(1 and 2) or 3` — (voorwaarde 1 EN voorwaarde 2) OF voorwaarde 3
* `(1 and 2) or (3 and 4)` — twee onafhankelijke groepen

## Voorbeelden {#examples}

**Voorbeeld 1: Alle gebruikers van een ingevoerde lijst en 10% van gebruikers uit een specifiek land**

Voeg twee regels toe: één voor de geïmporteerde gebruikerslijst en één percentageregel (10%) gecombineerd met een landregel. Geneste logica gebruiken: `1 or (2 and 3)`.

**Voorbeeld 2: 10% van gebruikers in de VS en 20% van gebruikers in het VK**

Voeg vier regels toe: Land = VS, percentage = 10%, Land = VK, percentage = 20%. Geneste logica gebruiken: `(1 and 2) or (3 and 4)`.

## Zie ook {#see-also}

* [Publiek in functiemarkeringen en functiegroepen](audience-in-feature-flags-and-feature-groups.md)
* [Complexe publieksregels](complex-rules.md)
* [Een functie instellen die geleidelijk moet worden geïmplementeerd](../feature-flags/set-feature-gradual-rollout.md)
