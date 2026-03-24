---
title: Functievlaggen weergeven in verschillende omgevingen
description: Leer hoe u de status van functiemarkeringen in alle gekoppelde omgevingen kunt bekijken voor een toepassing in Adobe Experience Rollouts.
source-git-commit: 5c99061a7f2aaaad98190166ea6fd79b7eb26dec
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---


# Functievlaggen weergeven in verschillende omgevingen {#view-flags-across-environments}

Zodra u de toepassingsinstanties in verschillende omgevingen hebt gekoppeld, geeft Experience Rollouts de status van elke functiemarkering weer in alle gekoppelde omgevingen die rechtstreeks in de pagina met lijsten met functiemarkeringen staan. Dit geeft u één mening om vlagstaten te vergelijken — bijvoorbeeld, of een vlag in Stadium en in Productie is. Zonder omschakelingsmilieu&#39;s.

## Vereisten {#prerequisites}

Uw toepassingsinstanties moeten in verschillende omgevingen zijn gekoppeld voordat de status van een andere omgeving zichtbaar is. Zie [&#x200B; milieu&#39;s aan een toepassing &#x200B;](associate-environments.md) voor opstellingsinstructies associëren.

## Hoe werkt het {#how-it-works}

Wanneer u aan **Eigenschappen &amp; Versies > de Vlaggen van de Eigenschap** navigeert en een toepassing selecteert die instanties heeft verbonden, toont de lijst van de pagina extra kolommen voor elk verbonden milieu. Elke kolom toont de huidige staat van de eigenschapvlag in die milieu.

De vlaggen van de eigenschap worden aangepast over milieu&#39;s door hun **sleutel** — niet door hun naam. Dit betekent:

* Een vlag kan een verschillende vertoningsnaam in elke milieu hebben, zolang de sleutel het zelfde is.
* De naam die in elke omgevingskolom wordt weergegeven, is de naam die in die omgeving wordt gebruikt.

## Hoofdletters gebruiken {#use-case}

Een typisch werkschema moet een eigenschapvlag in een lagere milieu (bijvoorbeeld, Stadium) ontwikkelen en testen, dan zijn status verifiëren alvorens de configuratie aan Productie te bevorderen. Door de zichtbaarheid tussen omgevingen kunt u controleren of de markering correct is geconfigureerd in het werkgebied voordat u deze importeert in Productie — allemaal vanuit de productieconsole.

## Zie ook {#see-also}

* [Omgevingen koppelen aan een toepassing](associate-environments.md)
* [Markeringen voor importfuncties](import-feature-flags.md)
* [Concept tussen milieu en milieu](cross-environment-concept.md)
