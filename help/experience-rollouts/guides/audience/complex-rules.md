---
title: Complexe publieksregels
description: Leer hoe u met grote of complexe publieksregelsets werkt in Adobe Experience Rollouts, waaronder limieten voor bulkwaarden en hoe u regels over meerdere voorwaarden kunt splitsen.
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Complexe publieksregels {#complex-rules}

## Limieten voor bulkwaarden {#bulk-value-limits}

Wanneer u een groot aantal waarden toevoegt aan één publieksregel, bijvoorbeeld een lange lijst met e-mailadressen, kan er een fout optreden die aangeeft dat de regel de maximaal toegestane grootte heeft overschreden.

Elke publieksregel heeft een formaatlimiet per kenmerk. Voor e-mailadressen is de limiet afhankelijk van de totale tekenlengte van de items en niet van een vast aantal. Als algemene richtlijn, gebruik ongeveer **100-115 e-mailadressen per regel**.

Als u meer ingangen moet richten dan deze grens toestaat, spleet de lijst in kleinere brokken en past hen als afzonderlijke OF-verbonden voorwaarden toe gebruikend genestelde logica.

## Geneste logica gebruiken voor complexe regels {#nested-logic}

Met geneste logica kunt u meerdere publieksomstandigheden combineren met nauwkeurige AND/OR-controle. U schakelt dit als volgt in:

1. Voeg de gewenste publieksvoorwaarden toe.
2. Laat **Genestelde Logiek** in de sectie van de publieksregels toe.
3. Aan elke voorwaarde wordt een getal toegewezen. Voer een logische expressie in die naar deze getallen verwijst, bijvoorbeeld:
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

Dit is hetzelfde mechanisme dat wordt gebruikt voor percentageregels in combinatie met andere criteria. Zie [&#x200B; percentageregels in publiekscriteria &#x200B;](adding-percentage-rules.md) voor werkte voorbeelden toevoegen.

## Zie ook {#see-also}

* [Publiek in functiemarkeringen en functiegroepen](audience-in-feature-flags-and-feature-groups.md)
* [Percentageregels toevoegen aan publiekscriteria](adding-percentage-rules.md)
