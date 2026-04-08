---
title: Markeringen voor importfuncties
description: Leer hoe u functiemarkeringen van de ene sandbox naar een andere importeert in Adobe Experience Rollouts om te voorkomen dat vlagconfiguraties handmatig opnieuw worden gemaakt.
exl-id: 37c84d75-a565-4202-8c99-f630e05b6bb6
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# Markeringen voor importfuncties {#import-feature-flags}

Met Experience Rollouts kunt u functiemarkeringen importeren van de ene sandbox (bijvoorbeeld sandbox 1) naar een andere sandbox (bijvoorbeeld sandbox 2). Zo voorkomt u dat u vlagconfiguraties handmatig opnieuw moet maken en verkleint u het risico van configuratieverschuiving tussen sandboxen.

## Stap 1: Ga naar de doelsandbox en -toepassing {#step-1}

Login aan de console voor de **bestemmings** zandbak - de zandbak u vlaggen *in* wilt invoeren. Selecteer de toepassing waarin u markeringen wilt importeren in de vervolgkeuzelijst van de toepassing op de pagina Functiemarkeringen.

>[!IMPORTANT]
>
>Uw huidige zandbak en geselecteerde toepassing moeten de **bestemming** zijn — niet de bron. Als u bijvoorbeeld een vlag wilt importeren van sandbox 1 naar sandbox 2, meldt u zich aan bij de sandbox 2-console en selecteert u de sandbox 2-toepassing.

## Stap 2: Het dialoogvenster Importeren openen {#step-2}

Selecteer **de Vlaggen van de Eigenschap van de Invoer**. Er wordt een dialoogvenster geopend met de bronsandbox en -toepassing, die vooraf zijn ingevuld op basis van de beschikbare toepassingen. Indien nodig, kunt u de bronzandbak en toepassing van drop-down in de dialoog veranderen.

## Stap 3: selecteer de functiemarkeringen die u wilt importeren {#step-3}

Selecteer in de lijst met functiemarkeringen in de bronsandbox de markeringen die u wilt importeren. U kunt een, meerdere of alle markeringen tegelijk selecteren.

## Stap 4: selecteer de status van de functiemarkeringen die u wilt importeren {#step-4}

Gebruik dropdown om te kiezen hoe de eigenschapmarkeringen zouden moeten worden ingevoerd — of **Toegelaten**, **Gehandicapten**, of in hun **Huidige staat**. Door gebrek, worden de eigenschapvlaggen ingevoerd in de **Gehandicapte** staat.

## Belangrijke opmerkingen {#important-notes}

Houd rekening met het volgende wanneer u functiemarkeringen importeert:

* Als er al een functiemarkering met dezelfde sleutel bestaat in de doelsandbox, wordt deze niet geïmporteerd.

## Zie ook {#see-also}

* [Functies en functiegroepen](../feature-flags/features-feature-groups-releases.md)
* [De eerste functiemarkering maken](../feature-flags/create-your-first-feature-flag.md)
