---
title: De regel van het publiek met cliëntIP contextvariabele
description: Leer hoe te om de cliëntIP contextvariabele in publieksregels in de Rollouts van de Ervaring van Adobe, met inbegrip van steun voor IP adressen, blokken CIDR, en netwerkwaaiers te gebruiken.
source-git-commit: 3f3f7145b3c58dc721cbeb850e9e8571e3255bb1
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---


# De regel van het publiek met cliëntIP contextvariabele {#clientip-rule}

Met de contextvariabele `clientip` kunt u zich richten op gebruikers op basis van hun IP-adres van de client. Dit is nuttig om eigenschappen te beperken of toe te laten die op het netwerk worden gebaseerd waarvan de gebruikers tot uw toepassing toegang hebben — bijvoorbeeld, die vroege toegang tot gebruikers op een collectief netwerk beperken.

## Ondersteunde invoertypen {#input-types}

De contextvariabele `clientip` ondersteunt drie typen invoerwaarden:

| Invoertype | Beschrijving | Ondersteunde operatoren |
|---|---|---|
| **IP adres** | Eén IPv4- of IPv6-adres | Is, is niet gelijk aan, in |
| **CIDR blok** | Een bereik van IP-adressen in CIDR-notatie (bijvoorbeeld `192.168.1.0/24`) | Is, in, niet gelijk aan |
| **waaier van het Netwerk** | Een vooraf gedefinieerd benoemd netwerkbereik dat door het platform wordt onderhouden | maakt deel uit van |

## Een client-IP-regel toevoegen {#adding-rule}

1. Open de eigenschapvlag, eigenschapgroep, of dwars-teameigenschapgroep in de console.
2. Ga naar het **publiek** lusje.
3. Onder **Context**, voeg een voorwaarde toe gebruikend de **clientip** variabele.
4. Selecteer de exploitant en ga de waarde (IP adres, blok CIDR, of selecteer een vooraf bepaalde netwerkwaaier) in.

## Zie ook {#see-also}

* [Context gebruiken in publieksregels](using-context-in-audience-rules.md)
* [Publiek in functiemarkeringen en functiegroepen](audience-in-feature-flags-and-feature-groups.md)
* [Complexe publieksregels](complex-rules.md)
