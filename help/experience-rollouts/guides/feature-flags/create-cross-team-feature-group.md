---
title: Een functiegroep voor meerdere teams maken
description: Leer hoe u een functiegroep voor meerdere teams kunt maken in Adobe Experience Rollouts om functiemarkeringen te coördineren in toepassingen die eigendom zijn van verschillende teams.
source-git-commit: db719ba7b9db91aea818d8ef216a28fcedc6aa65
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 0%

---


# Een functiegroep voor meerdere teams maken {#create-cross-team-feature-group}

## Vereisten {#prerequisites}

Bevestig het volgende voordat u een multiteam-functiegroep maakt:

* U hebt toegang tot de console — zie [ Login aan de console ](../console/log-in-to-the-console.md)
* U maakt deel uit van een team en uw toepassing is aan boord
* U hebt de **rol van Admin van de Eigenschap 0} {— zie [ de rollen van de Gebruiker ](../teams/user-roles.md)**
* U hebt de eigenschapvlaggen gecreeerd om te omvatten — zie [ uw eerste eigenschapvlag ](create-your-first-feature-flag.md) creëren

Een multiteam eigenschapgroep staat het bundelen eigenschapmarkeringen van toepassingen over veelvoudige teams met rijk publiek toe richtend. In tegenstelling tot releases is deze server volledig zelf-serverbaar en heeft deze geen limiet voor het aantal dat u kunt maken. Zie [ Versies en dwars-teameigenschapgroepen ](releases-and-cross-team-feature-groups.md) voor een vergelijking.

## Stap 1: Creeer de dwars-teameigenschapgroep {#create}

Begin het creatieproces van de sectie van Versies van de console:

1. Navigeer aan **Eigenschappen &amp; Versies > Versies** in de console.
2. Selecteer **Nieuwe Groep van de Eigenschap (Cross-Team)**.

## Stap 2: basisgegevens {#basic-details}

Geef een titel, sleutel, beschrijving en eventueel een tag op. Configureer de volgende opties:

* **de uitrol van het Percentage** - plaats hoeveel van het publiek de eigenschap ontvangt.
* **Type van Uitvoer** — Reeks aan Handboek. Het percentage wordt beheerd geleidelijke aangezien uw rollout vordert.

>[!NOTE]
>
>A/B het testen wordt niet gesteund voor de groepen van de dwars-teameigenschap. Om tests in werking te stellen A/B, gebruik een standaard [ eigenschapgroep ](create-a-feature-group.md) (de toepassingen moeten in het zelfde team zijn).

## Stap 3: Publiek {#audience}

Op het **publiek** lusje, laat **Regels van het Publiek** toe en vormt:

* **Segmenten** - selecteer een vooraf bepaald publiekssegment.
* **Extra filters** - voeg op profiel-gebaseerde of op context-gebaseerde criteria direct toe.
* **Toepassingen** — Selecteer één of meerdere toepassingen van uw team of andere teams.

>[!IMPORTANT]
>
>Als u een toepassing van een ander team toevoegt, hebben de beheerders van functies van dat team het recht om functiemarkeringen voor hun toepassing toe te voegen aan deze groep met functies voor meerdere teams. U kunt de eigenschapmarkeringen niet zelf toevoegen.

## Stap 4: Functies {#features}

Onder het **lusje van Eigenschappen**, ziet u een doos voor elke inbegrepen toepassing:

* Voor toepassingen in uw eigen team kunt u functiemarkeringen rechtstreeks toevoegen.
* Voor toepassingen van andere teams, zijn die dozen grayed uit — de Admins van de Eigenschap van het respectieve team moet hun vlaggen toevoegen.

>[!IMPORTANT]
>
>Een eigenschapmarkering kan slechts door één methode tegelijkertijd worden gediend. Als u een vlag toevoegt aan een functiegroep voor meerdere teams, worden alle doelgroepen of percentages die zijn ingesteld op de vlag, rechtstreeks verwijderd. Markeringen die al in een andere versie of functiegroep staan, worden niet weergegeven.

## Stap 5: Planning (optioneel) {#schedule}

U kunt de functiegroep voor meerdere teams plannen om op een toekomstige datum en tijd te activeren. Zie [ Programma ](schedule.md) voor details.

## Frames beheren {#states}

Het team dat tot de dwars-teameigenschapgroep leidt bezit het en kan zijn staat beheren. De Admin van de eigenschap leden van het het bezitten team kunnen overgang tussen staten gebruikend het staatsdrop-down:

| Staat | Beschrijving |
|---|---|
| **sparen** | Opgeslagen en niet live. Alle wijzigingen zijn toegestaan. |
| **publiceer** | Leef voor het gevormde publiek. De beheerders van de eigenschap kunnen blijven het bijwerken van publiekscriteria en percentenuitrol. |
| **Volledige rollout** | Beschikbaar voor alle gebruikers. Kan het publiek niet verder beperken na dit punt. |
| **Basislijn** | Functies zijn nu de standaardinstelling. De groep met functies voor meerdere teams is gesloten. |
| **afbreken** | De rollout wordt gestopt. Geen enkele gebruiker ontvangt functies van deze groep. |

## Veelgestelde vragen {#faqs}

**is er een grens op het aantal dwars-teameigenschapgroepen?**
Nee. In tegenstelling tot releases is er geen limiet. Nochtans, archiveer of maak groepen onbruikbaar wanneer niet meer nodig.

**wat is het verschil tussen een versie en een dwars-teameigenschapgroep?**
Zie [ Versies en dwars-teameigenschapgroepen ](releases-and-cross-team-feature-groups.md) voor een gedetailleerde vergelijking.

## Zie ook {#see-also}

* [Versies en groepen met meerdere functies](releases-and-cross-team-feature-groups.md)
* [Een functiegroep maken](create-a-feature-group.md)
