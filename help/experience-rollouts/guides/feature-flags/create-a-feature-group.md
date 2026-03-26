---
title: Een functiegroep maken
description: Leer hoe u in Adobe Experience Rollouts een functiegroep maakt voor het beheren van meerdere functiemarkeringen in verschillende toepassingen in uw team als één eenheid.
exl-id: 58148df1-84ee-4a78-a4b4-71f74cd8ce0a
source-git-commit: 454b5c719a5f8be82d1ed835da58bfca6316def2
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Een functiegroep maken {#create-feature-group}

## Vereisten {#prerequisites}

Voer de volgende handelingen uit voordat u een functiegroep maakt:

* U hebt toegang tot de console van Rollouts van de Ervaring — zie [&#x200B; Login aan de console &#x200B;](../console/log-in-to-the-console.md)
* Uw toepassing wordt bewaakt - zie [&#x200B; Op uw toepassing &#x200B;](../applications/onboard-your-application.md)
* U hebt de **rol van de Eigenaar van de Versie van de Ontwikkelaar** of **Product**
* U hebt de eigenschapvlaggen gecreeerd u aan de groep wilt toevoegen — zie [&#x200B; uw eerste eigenschapvlag &#x200B;](create-your-first-feature-flag.md) creëren

Voor een inleiding aan eigenschapgroepen, zie {de groepen van de Eigenschap 0} om veelvoudige eigenschappen [&#128279;](../../concepts/feature-groups-to-control-multiple-features.md) te controleren.

## Stap 1: Maak de functiegroep {#create}

Open de console en begin een nieuwe eigenschapgroep:

1. Login aan de console van Rollouts van de Ervaring en navigeer aan **het Testen van de Eigenschap > de Groepen van de Eigenschap**.
2. Selecteer **Nieuwe Groep van de Eigenschap**.

## Stap 2: basisgegevens {#basic-details}

Configureer de algemene instellingen voor de functiegroep:

1. Geef een titel, sleutel, beschrijving en eventueel een tag op.
2. Plaats a **percentenuitloop** voor de eigenschapgroep.
3. Als u een test A/B wilt in werking stellen, selecteer meer dan één variant. Anders, verlaat het bij één variant. Zie [&#x200B; A/B het testen met eigenschapmarkeringen &#x200B;](a-b-testing.md) voor details.

## Stap 3: Publiek {#audience}

Bepaal wie de eigenschappen in deze groep zal ontvangen:

1. Op het **publiek** lusje, voeg publiekscriteria toe om te bepalen welke gebruikers de eigenschap ontvangen.
2. Onder **Toepassingen**, voeg één of meerdere toepassingen van uw team toe. De groepen van de eigenschap kunnen veelvoudige toepassingen overspannen zolang zij allen tot het zelfde team behoren.

>[!NOTE]
>
>De **rol van de Ontwikkelaar** is sandbox. Voeg uw eigen identiteitskaart van de Gebruiker onder **Publiek > Profiel > Gebruiker toe - identiteitskaart** om privé te testen. Om externe gebruikers te richten, hebt u de **rol van de Eigenaar van de Versie van het 0&rbrace; Product nodig.**

## Stap 4: Functies {#features}

Wijs de eigenschapmarkeringen toe die door deze groep zullen worden gecontroleerd:

1. Onder het **lusje van Eigenschappen**, ziet u een doos voor elke toepassing u selecteerde.
2. U kunt functiemarkeringen toevoegen voor elke toepassing.
3. Als u meerdere varianten hebt geselecteerd (voor A/B-tests), ziet u tabbladen voor elke variant. Voeg de relevante eigenschapmarkeringen aan elk toe.

>[!IMPORTANT]
>
>Een eigenschapvlag kan slechts door één methode worden gediend — of direct als eigenschapvlag, door een eigenschapgroep, of door een versie. Wanneer u een eigenschapvlag aan een eigenschapgroep toevoegt, wordt om het even welk publiek of percentage rollout die op de vlag wordt geplaatst verwijderd. Functiemarkeringen die al zijn toegewezen aan een andere release of functiegroep, worden niet weergegeven in de lijst.

## Stap 5: Planning (optioneel) {#schedule}

U kunt plannen dat de functiegroep op een toekomstige datum en tijd wordt geactiveerd. Zie [&#x200B; Programma &#x200B;](schedule.md) voor details.

## Zie ook {#see-also}

* [Een functiegroep instellen die geleidelijk moet worden geïmplementeerd](set-feature-group-gradual-rollout.md)
* [A/B testen met functiemarkeringen](a-b-testing.md)
* [Functiegroepen om meerdere functies te beheren](../../concepts/feature-groups-to-control-multiple-features.md)
