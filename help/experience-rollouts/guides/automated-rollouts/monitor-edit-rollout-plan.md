---
title: Een rollout-abonnement controleren en bewerken
description: Leer hoe u de voortgang van een geautomatiseerd implementatieplan in Adobe Experience Rollouts kunt bijhouden en hoe u een lopend plan kunt pauzeren, hervatten of afbreken.
source-git-commit: d824d85c6701edc9be314713bb8e9624b183e2d2
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---


# Een rollout-abonnement controleren en bewerken {#monitor-edit-rollout-plan}

Zodra een geautomatiseerde rollout levend is, kunt u zijn vooruitgang volgen en tussenbeide komen indien nodig. Op deze pagina wordt beschreven hoe u de voortgangsindicator kunt lezen, een plan kunt onderbreken en hervatten en zo nodig kunt afbreken.

Deze pagina veronderstelt u reeds een rollout plan hebt gecreeerd en gepubliceerd. Zie [ creeer een geautomatiseerde rollout ](create-automated-rollout.md) als u nog niet opstelling hebt.

## Voortgang van rollout weergeven {#view-progress}

Nadat het rollout plan begint uit te voeren, open het **publiek** lusje van de eigenschap om de huidige staat van het plan te zien. Het plan toont een vooruitgangsindicator die welke faseblok momenteel actief is merkt.

Gebruik de voortgangsindicator om het volgende te begrijpen:

* **Voltooide blokken** — Alle fase en wachten blokken boven de indicator zijn uitgevoerd. Deze blokken zijn vergrendeld en kunnen niet worden bewerkt.
* **Huidige blok** — het momenteel benadrukte blok is de actieve fase of wachttijdperiode.
* **Komende blokken** — Alle fase en wachtende blokken onder de indicator hebben nog niet uitgevoerd. Deze kunnen nog steeds worden bewerkt.

## Een rollout-plan pauzeren {#pause}

Om de rollout op om het even welk punt te pauzeren terwijl het lopend is, selecteer **Uitvoer van de Pauze** in de console.

Wanneer het plan wordt gepauzeerd:

* Het publiek van het laatste voltooide faseblok blijft actief. Gebruikers in dat publiek blijven de functie ontvangen.
* De eigenschapvlag, eigenschapgroep, of de dwars-teameigenschapgroep blijft in zijn huidig op of gepubliceerde staat. De functie wordt nog steeds aan het actieve publiek aangeboden.
* De komende fase en wachtblokken blijven editable.

Om een gepauzeerd plan te hervatten, selecteer **Uitvoer hervatten**. Het plan gaat verder vanaf het punt waar het is opgehouden.

## Een rollout-plan afbreken {#abort}

Om het rollout plan permanent tegen te houden, selecteer **Uitvoer van de Afbreking** in de console.

Wanneer het plan wordt afgebroken:

* Het publiek van het laatste voltooide faseblok blijft actief, en de eigenschap blijft aan dat publiek worden gediend.
* De functie zelf is niet uitgeschakeld. Als u de functie niet meer volledig wilt bedienen, moet u de release afzonderlijk afbreken of de markering of groep met functies uitschakelen.
* De volgende fase en wachtblokken kunnen niet meer worden uitgegeven.
* Een geaborteerd plan kan niet worden hervat.

>[!IMPORTANT]
>
>Als u een rollout-plan afbreekt, wordt de functie niet automatisch uitgeschakeld. Voer een aparte actie uit op de status van de functie als u de status niet meer wilt weergeven aan gebruikers.

## Komende faseblokken bewerken {#edit-upcoming}

Terwijl het plan bezig is (of gepauzeerd), kunt u om het even welke fase nog uitgeven of blokkeren wachten die nog niet is uitgevoerd:

* Pas de publieksregels of het percentage voor een toekomstig faseblok aan.
* Wijzig de duur of de vaste datum van een toekomstig wachtblok.

Voltooide blokken zijn vergrendeld en kunnen niet worden gewijzigd.

## Zie ook {#see-also}

* [Een automatische rollout maken](create-automated-rollout.md)
* [Geautomatiseerd rollout-concept](automated-rollout-concept.md)
* [Releasestatus](../feature-flags/release-states.md)
