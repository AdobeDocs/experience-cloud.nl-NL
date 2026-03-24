---
title: Publiek in functiemarkeringen en functiegroepen
description: Leer hoe u publiekscriteria voor functiemarkeringen en functiegroepen in Adobe Experience Rollouts definieert met behulp van profielkenmerken, segmenten en de calculator voor doelgroepen.
source-git-commit: 3f3f7145b3c58dc721cbeb850e9e8571e3255bb1
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---


# Publiek in functiemarkeringen en functiegroepen {#audience-overview}

De Rollouts van de ervaring verstrekt rijke publiek die voor eigenschapvlaggen en eigenschapgroepen richten. U kunt profielkenmerken, contextvariabelen, en publiekssegmenten combineren om precies te controleren welke gebruikers een eigenschap ontvangen.

## Profielregels {#profile-rules}

Met profielregels kunt u zich richten op gebruikers op basis van kenmerken zoals land, e-maildomein, accounttype, gebruikersnaam en meer. U kunt veelvoudige attributen combineren gebruikend exploitanten AND/OR en genestelde logica voor complexe het richten scenario&#39;s bouwen.

Om profielregels toe te voegen, ga naar het **publiek** lusje van een eigenschapvlag of eigenschapgroep en voeg voorwaarden onder **Profiel** toe.

U kunt een reeks publieksregels als herbruikbaar **Publiek** voor gebruik over veelvoudige vlaggen en groepen bewaren.

Voor op context-gebaseerd richten (bijvoorbeeld, die door de actieve taal van de gebruiker of cliënttype richten), zie [&#x200B; context van het Gebruik in publieksregels &#x200B;](using-context-in-audience-rules.md).

## Segmenten {#segments}

De vlaggen van de eigenschap en eigenschapgroepen steunen publiekssegmenten. Met segmenten kunt u:

* Gebruik één vooraf gedefinieerde publieksdefinitie voor meerdere functiemarkeringen en groepen
* Omvat **gebeurtenis-gebaseerde criteria** in uw publiek richtend - iets niet mogelijk met profielregels alleen

Om een segment te gebruiken, ga naar het **publiek** lusje en selecteer één of meerdere segmenten van de lijst. U kunt veelvoudige segmenten combineren gebruikend exploitanten AND/OR, en extra profiel of contextfilters toevoegen naast hen.

>[!NOTE]
>
>U hebt de **rol van de Manager van de Test** of hoger nodig om publiekssegmenten tot stand te brengen.

## Auditiefalculator {#audience-calculator}

Na het bepalen van uw publiekscriteria, berekent de uitgezochte **&#x200B;**&#x200B;in de bodembar om een geschatte telling van gebruikers te krijgen die kwalificeren. Zo kunt u het bereik van uw doelgroep valideren voordat u de functie activeert.

>[!NOTE]
>
>De publiekscalculator retourneert geen waarde wanneer contextvariabelen in de criteria worden opgenomen, omdat contextwaarden bij uitvoering worden bepaald en niet vooraf kunnen worden voorspeld.

## Zie ook {#see-also}

* [Context gebruiken in publieksregels](using-context-in-audience-rules.md)
* [Percentageregels toevoegen aan publiekscriteria](adding-percentage-rules.md)
* [Complexe publieksregels](complex-rules.md)
* [De eerste functiemarkering maken](../feature-flags/create-your-first-feature-flag.md)
