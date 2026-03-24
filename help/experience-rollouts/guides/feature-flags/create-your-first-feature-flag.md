---
title: De eerste functiemarkering maken
description: Leer hoe u een functiemarkering kunt maken in Adobe Experience Rollouts, een publiek kunt instellen en testen voordat u de markering voor gebruikers gaat gebruiken.
source-git-commit: ae420329b94b24fcd173734b414aecf1c5fc16ca
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---


# De eerste functiemarkering maken {#create-feature-flag}

## Vereisten {#prerequisites}

Vul de volgende handelingen in voordat u een functiemarkering maakt:

* U hebt toegang tot de console van Rollouts van de Ervaring — zie [ Login aan de console ](../console/log-in-to-the-console.md)
* U behoort tot een team - zie [ teams beheren ](../teams/manage-teams.md)
* Uw toepassing wordt bewaakt - zie [ Op uw toepassing ](../applications/onboard-your-application.md)
* U hebt de **rol van de Eigenaar van de Versie van de Ontwikkelaar** of **Product** - zie [ Gebruikersrollen ](../teams/user-roles.md)

## Stap 1: De functiemarkering maken {#create}

Om een nieuwe eigenschapvlag tot stand te brengen, volg deze stappen in de console:

1. Login aan de console van Rollouts van de Ervaring en navigeer aan **Eigenschappen &amp; Versies > de Vlaggen van de Eigenschap**.
2. Selecteer uw toepassing van de **drop-down Toepassing**.
3. Selecteer **Nieuwe Eigenschap**.
4. Geef een titel, sleutel, beschrijving en eventueel een tag op.
5. Voeg desgewenst een publiekscriteria toe (zie Stap 2).
6. Sla de instellingen voor de functiemarkering op.

## Stap 2: Voeg publiekscriteria toe {#audience}

De criteria van de Publiek controleren welke gebruikers de eigenschap zien. U kunt criteria toevoegen op basis van:

* Profielkenmerken (zoals land, e-maildomein, gebruikersnaam)
* Contextvariabelen
* Vooraf gedefinieerde publiekssegmenten

Om publiekscriteria toe te voegen, ga naar het **publiek** lusje wanneer het creëren van of het uitgeven van een eigenschapvlag.

>[!NOTE]
>
>De **rol van de Ontwikkelaar** is sandbox. De ontwikkelaars kunnen een eigenschap aan zich slechts blootstellen door hun eigen Gebruiker toe te voegen - identiteitskaart onder **Publiek > Profiel > Gebruiker - identiteitskaart**. Om een eigenschap aan externe gebruikers bloot te stellen, hebt u de **rol van de Eigenaar van de Versie van het 0} Product nodig.**

## Stap 3: de omvang van het publiek berekenen {#audience-size}

Na het toevoegen van publiekscriteria, berekent de uitgezochte **** in de bodembar om een geschatte telling van gebruikers te krijgen die voor de eigenschap kwalificeren. Zo kunt u uw doelversie valideren voordat u live gaat.

## Stap 4: Schema (optioneel) {#schedule}

U kunt een functiemarkering plannen om op een toekomstige datum en tijd te activeren. Zie [ Programma ](schedule.md) voor details.

## Veelgestelde vragen: ik kan geen functiemarkering toevoegen als ontwikkelaar {#faq}

De **rol van de Ontwikkelaar** is sandbox. Ontwikkelaars kunnen functies privé testen door hun gebruikersnaam aan het publiek toe te voegen. Ze kunnen functies niet aan externe gebruikers beschikbaar maken. Gebruik de **rol van de Eigenaar van de Versie van het 0} Product {om eigenschappen aan externe gebruikers vrij te geven.** Neem contact op met uw teambeheerder om uw rol bij te werken.

## Zie ook {#see-also}

* [Een functie instellen die geleidelijk moet worden geïmplementeerd](set-feature-gradual-rollout.md)
* [Een functiegroep maken](create-a-feature-group.md)
* [Gebruikersrollen](../teams/user-roles.md)
