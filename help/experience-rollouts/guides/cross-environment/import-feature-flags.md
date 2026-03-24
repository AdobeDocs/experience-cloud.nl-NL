---
title: Markeringen voor importfuncties
description: Leer hoe u functiemarkeringen van een lagere omgeving kunt importeren in een hogere omgeving in Adobe Experience Rollouts om te voorkomen dat vlagconfiguraties handmatig opnieuw worden gemaakt.
source-git-commit: 5c99061a7f2aaaad98190166ea6fd79b7eb26dec
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---


# Markeringen voor importfuncties {#import-feature-flags}

Met Experience Rollouts kunt u functiemarkeringen importeren vanuit een lagere omgeving (bijvoorbeeld Stage) naar een hogere omgeving (bijvoorbeeld Production). Dit vermijdt het moeten vlagconfiguraties manueel opnieuw creëren en vermindert het risico van configuratieverschuiving tussen milieu&#39;s.

## Vereisten {#prerequisites}

Als u de importworkflow wilt gebruiken, moeten de toepassingsinstanties aan verschillende omgevingen zijn gekoppeld. Zie [&#x200B; milieu&#39;s aan een toepassing &#x200B;](associate-environments.md) associëren.

## Stap 1: Ga naar de doelomgeving en toepassing {#step-1}

Login aan de console voor het **bestemmings** milieu - het milieu u vlaggen *in* wilt invoeren. Selecteer de toepassing waarin u markeringen wilt importeren in de vervolgkeuzelijst van de toepassing op de pagina Functiemarkeringen.

>[!IMPORTANT]
>
>Uw huidig milieu en geselecteerde toepassing moeten de **bestemming** zijn — niet de bron. Als u bijvoorbeeld een vlag wilt importeren van Stage naar Production, meldt u zich aan bij de productieconsole en selecteert u de productietoepassing.

## Stap 2: Het dialoogvenster Importeren openen {#step-2}

Selecteer **de Vlaggen van de Eigenschap van de Invoer**. Er wordt een dialoogvenster geopend met de bronomgeving en -toepassing, die vooraf zijn ingevuld op basis van de gekoppelde omgevingen die voor uw toepassing zijn geconfigureerd. Indien nodig kunt u de bronomgeving en toepassing wijzigen in de keuzelijst in het dialoogvenster.

## Stap 3: selecteer de functiemarkeringen die u wilt importeren {#step-3}

Selecteer in de lijst met functiemarkeringen in de bronomgeving de markeringen die u wilt importeren. U kunt een, meerdere of alle markeringen tegelijk selecteren.

## Stap 4: Bestaande vlaggen afhandelen (indien vereist) {#step-4}

Als een eigenschapvlag met de zelfde sleutel reeds in het bestemmingsmilieu bestaat, zal de Rollouts van de Ervaring u vragen om te bevestigen of om het te beschrijven. Herzie de bestaande vlagconfiguratie alvorens te bevestigen, aangezien het beschrijven de montages van de bestemmingsvlag met die van de bron zal vervangen.

## Belangrijke opmerkingen {#important-notes}

Houd rekening met het volgende wanneer u functiemarkeringen importeert:

* De ingevoerde vlaggen worden altijd geplaatst aan **VAN** staat in het bestemmingsmilieu, ongeacht hun staat in het bronmilieu. U moet ze na het importeren handmatig inschakelen.
* Als een vlag op een toekomstige datum en tijd in het bronmilieu werd gepland te activeren, wordt dat programma **niet** gedragen over. U moet een nieuw programma in het bestemmingsmilieu plaatsen indien nodig.

## Zie ook {#see-also}

* [Omgevingen koppelen aan een toepassing](associate-environments.md)
* [Functievlaggen weergeven in verschillende omgevingen](view-feature-flags-across-environments.md)
* [Concept tussen milieu en milieu](cross-environment-concept.md)
