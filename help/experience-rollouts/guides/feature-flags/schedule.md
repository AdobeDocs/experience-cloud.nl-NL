---
title: Schema
description: Leer hoe u een functiemarkering, functiegroep of functiegroep voor meerdere teams kunt plannen om automatisch op een toekomstige datum en tijd te activeren in Adobe Experience Rollouts.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Schema {#schedule}

Het plannen is een facultatieve eigenschap die u een toekomstige datum en tijd voor een eigenschapvlag, eigenschapgroep, of dwars-teameigenschapgroep laat plaatsen om automatisch te activeren. Handmatige aan/uit-toggling blijft beschikbaar en hoeft niet te worden vervangen door een schema.

Planning wordt ondersteund voor:

* Functiemarkeringen
* Functiegroepen
* De eigenschapgroepen van het dwars-team (programma&#39;s de overgang aan **publiceren** staat)

## Stap 1: Het schema instellen {#set-schedule}

1. Open de eigenschapvlag, eigenschapgroep, of dwars-teameigenschapgroep in de console.
2. Selecteer de **knoop van het Programma** op de rechterkant van het scherm.
3. In pop-up, plaats de **begindatum en tijd** en selecteer **timezone**.

## Stap 2: Opslaan {#save}

Selecteer **Vastgesteld Programma**, dan sparen de montages. Het schema wordt pas van kracht wanneer u het opslaat.

## Nadat een schema is ingesteld {#after-schedule-set}

Als de gegevens eenmaal zijn opgeslagen, worden de geplande datum en tijd weergegeven in de markering of weergave van de functiegroep.

Als u probeert om de aan/uit staat manueel in- en uit te schakelen terwijl een programma actief is, verschijnt een waarschuwing vragend of u het programma wilt met voeten treden of de actie annuleren.

## Op de geplande datum en tijd {#on-schedule}

Op de geplande tijd, activeert de eigenschapvlag of eigenschapgroep automatisch (bewegingen aan de staat ON). Voor de groepen van de dwars-teameigenschap, de staatsovergangen aan **Gepubliceerd**.

Na de programmabranden, is de **knoop van het Programma** gehandicapt. Planningen kunnen slechts worden geplaatst wanneer de eigenschapvlag of de eigenschapgroep in weg (of Opgeslagen, voor dwars-teameigenschapgroepen) staat is.

## Zie ook {#see-also}

* [De eerste functiemarkering maken](create-your-first-feature-flag.md)
* [Een functiegroep maken](create-a-feature-group.md)
* [Een functiegroep voor meerdere teams maken](create-cross-team-feature-group.md)
