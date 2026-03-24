---
title: Gebruikersrollen
description: Leer over de vijf gebruikersrollen beschikbaar in de Rollouts van de Ervaring van Adobe en hoe te om de juiste rol voor elk teamlid te kiezen.
source-git-commit: 53edbee220e7ef17c4a3ea066743192c1e9681f4
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Gebruikersrollen {#user-roles}

De Rollouts van de ervaring verstrekt vijf rollen. Elke rol is ontworpen voor een specifieke reeks verantwoordelijkheden. Rollen sluiten elkaar standaard uit — een lid met de beheerdersrol beschikt niet automatisch over de machtigingen Eigenaar van productrelease. Wijs veelvoudige rollen aan een lid toe wanneer de bredere toegang nodig is.

## Beschikbare rollen {#roles}

| Rol | Verplichtingen |
|---|---|
| **Admin** | De toepassingen van onboards aan de console, beheert teamleden, en keurt of verwerpt toegangsverzoeken goed. Vereist voordat het team functiemarkeringen kan gaan gebruiken. |
| **Eigenaar van de Versie van het Product** | Hiermee maakt en werkt u functiemarkeringen en functiegroepen voor hun toepassing bij. Kan publiek koppelen aan functiemarkeringen om functies beschikbaar te maken voor externe gebruikers. |
| **Ontwikkelaar** | Werkt in een context met sandbox om functies achter functiemarkeringen te testen zonder dat dit van invloed is op andere gebruikers. Kan een functiemarkering beschikbaar maken voor een privépubliek (bijvoorbeeld een specifieke gebruikers-id of een e-mailadres) in het werkgebied of de productie. |
| **Admin van de Eigenschap** | Hiermee maakt en beheert u groepen met functies voor verschillende teams. Gebruik deze rol wanneer het coördineren van vlaggen over toepassingen die door verschillende teams worden bezeten. |
| **Manager van de Versie** | Beheert multi-team, multi-application versies en werkt de publieksregels bij die bepalen wie een versie ontvangt. |

## De juiste rol kiezen {#choosing}

Gebruik de volgende richtlijnen om rollen toe te wijzen:

* **Toevoegend of het bijwerken eigenschapvlaggen voor uw toepassing** → **Eigenaar van de Versie van het Product**
* **het Testen eigenschappen privé zonder anderen te beïnvloeden** → **Ontwikkelaar**
* **het leiden van dwars-teameigenschapgroepen** → **Admin van de Eigenschap**
* **het Leiden versies over veelvoudige teams en toepassingen** → **de Manager van de Versie**
* **Aan boord van toepassingen en het leiden teamlidmaatschap** → **Admin**

>[!NOTE]
>
>Een lid kan meer dan één rol hebben. Bijvoorbeeld, zou een ingenieur die zowel eigenschappen test als de toepassingen van het team beheert zowel de **Ontwikkelaar** en **Admin** rollen moeten hebben.

## Machtigingsfout {#permissions-error}

Als een lid een &quot;niet genoeg toestemmingen&quot;fout wanneer het proberen om een eigenschap of een groep bij te werken ontmoet, hebben zij de **rol van de Eigenaar van de Versie van het 0} Product {nodig.** Neem contact op met uw teambeheerder om deze rol toe te voegen.

## Zie ook {#see-also}

* [Leden aan uw team toevoegen](add-team-members.md)
* [Teams beheren](manage-teams.md)
