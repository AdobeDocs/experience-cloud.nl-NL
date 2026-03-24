---
title: Een automatische rollout maken
description: Leer hoe u een geautomatiseerd implementatieplan configureert in Adobe Experience Rollouts met faseblokken en wachtblokken zodat uw publiek zich automatisch uitbreidt in de loop van de tijd.
source-git-commit: d824d85c6701edc9be314713bb8e9624b183e2d2
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Een automatische rollout maken {#create-automated-rollout}

Met een geautomatiseerde rollout kunt u alle rollout-fasen en de bijbehorende planningen in één sessie definiëren. De Rollouts van de ervaring gaat automatisch van één fase aan volgende over, zonder u te vereisen om aan de console voor elke stap terug te keren. Zie [ Geautomatiseerd rollout concept ](automated-rollout-concept.md) voor een overzicht.

Geautomatiseerde rollouts worden ondersteund voor functiemarkeringen, functiegroepen en groepen met meerdere functies.

## Stap 1: automatische uitrol inschakelen {#enable-automated-rollout}

Wanneer het creëren van een nieuwe eigenschapvlag, eigenschapgroep, of dwars-teameigenschapgroep, open het **BasisDetails** lusje en bepaal de plaats van het **Uitgezochte type van rollout** optie. Het blijft aan **Handboek** in gebreke. Om een geautomatiseerd rollout plan toe te laten, uitgezochte **Geautomatiseerde Uitvoer**.

>[!NOTE]
>
>Wanneer u Geautomatiseerde Uitvoer selecteert, wordt het percentagerollout gebied in Basisdetails automatisch geplaatst aan 100% en wordt niet-editable. U zult het percentage voor elke fase individueel in het Publiek tabel controleren.

## Stap 2: Bouw het implementatieplan {#build-rollout-plan}

Open het **lusje van het Publiek** en laat de **schakelaar van de Fases** toe. Dit activeert **voegt het Blok van de Fase** toe en **voegt wachtende controles van het Blok** toe.

Om uw rollout plan te bouwen, voeg fase toe en wacht blokken in de orde u hen wilt uitvoeren:

### Een faseblok toevoegen {#add-phase-block}

Een faseblok bepaalt de publiekscriteria voor één fase van de rollout. Het eerste faseblok wordt gevormd gebruikend de publiekscriteria reeds op de pagina. Voor elk volgende faseblok, is het publiek van de vorige fase pre-bevolkt als uitgangspunt.

Vorm het publiek voor elk faseblok:

* **Percentage** — plaats welk percentage van het bepaalde publiek de eigenschap in deze fase ontvangt.
* **de regels van het Publiek** - voeg profiel, context, of op segment-gebaseerde regels aan doelspecifieke gebruikers toe.

>[!IMPORTANT]
>
>Elke volgende fase moet het publiek van de vorige fase uitbreiden, niet vervangen. Verwijder publieksregels niet uit eerdere fasen wanneer u latere fasen configureert, omdat dit onbedoeld gebruikers kan uitsluiten die de functie al kregen.

### Een blokkering voor een wachttijd toevoegen {#add-wait-block}

Een wachtblok definieert de pauze tussen twee faseblokken. Nadat u een wachtblok hebt toegevoegd, selecteert u een van de volgende opties:

| Optie | Beschrijving |
|---|---|
| **wacht** | Een relatieve duur — bijvoorbeeld, wacht 2 dagen, wacht 4 uur. Experience Rollouts gaat door naar het volgende faseblok nadat deze tijdsduur is verstreken. |
| **wacht op** | Een vaste datum en tijd. De Rollouts van de ervaring gaat aan het volgende faseblok op het gespecificeerde ogenblik vooruit. |

### Verdere faseblokken toevoegen {#add-subsequent-phases}

Herhaal het proces om extra faseblokken toe te voegen en blokkeringen te wachten tot uw volledig rollout plan wordt gevormd.

## Stap 3: de rollout plannen of publiceren {#schedule-or-publish}

Nadat het rollout-plan is voltooid, kiest u hoe het moet worden geactiveerd:

* **Programma** — Plaats een toekomstige datum en tijd voor de rollout om automatisch te beginnen. Zie [ Programma ](../feature-flags/schedule.md) voor details.
* **publiceert manueel** — draai de eigenschapvlag op of verplaats de eigenschapgroep aan **publiceren** staat om onmiddellijk te beginnen.

Het plan begint uitvoerend van het eerste faseblok. U kunt het actieve abonnement op elk gewenst moment controleren en bewerken. Zie [ Monitor en geef een rollout plan ](monitor-edit-rollout-plan.md) uit.

## Zie ook {#see-also}

* [Geautomatiseerd rollout-concept](automated-rollout-concept.md)
* [Een rollout-abonnement controleren en bewerken](monitor-edit-rollout-plan.md)
* [Een functie instellen die geleidelijk moet worden geïmplementeerd](../feature-flags/set-feature-gradual-rollout.md)
* [Criteria voor het publiek](../audience/audience-in-feature-flags-and-feature-groups.md)
