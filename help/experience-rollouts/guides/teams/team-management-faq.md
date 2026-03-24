---
title: Veelgestelde vragen over teambeheer
description: Zoek antwoorden op veelgestelde vragen over het beheren van teams, leden en rollen in Adobe Experience Rollouts.
source-git-commit: 53edbee220e7ef17c4a3ea066743192c1e9681f4
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---


# Veelgestelde vragen over teambeheer {#team-management-faq}

## Ik probeer een gebruiker toe te voegen, maar de zoekopdracht retourneert geen resultaten {#user-not-found}

Dit kan zich voordoen in de Stage-omgeving als de gebruiker zich nog niet eerder heeft aangemeld bij Stage. U kunt dit oplossen door de gebruiker te vragen zich minstens één keer aan te melden bij de Stage-console om een account te maken in het Stage-identiteitssysteem. Nadat ze zich hebben aangemeld, zoekt u ze opnieuw.

## Ik ben beheerder, maar ik kan geen functiemarkeringen maken of bewerken {#admin-cannot-edit-flags}

Rollen in Experience Rollouts sluiten elkaar uit. De **Admin** rol verleent teambeheertoestemmingen maar omvat niet de toestemmingen van de Eigenaar van de Versie van het a **Product**. Om eigenschapvlaggen tot stand te brengen en uit te geven, heeft een lid de **rol van de Eigenaar van de Versie van het 0&rbrace; Product naast de** Admin **rol nodig.**

Neem contact op met uw teambeheerder om extra rollen toe te wijzen. Zie {de rollen van 0} Gebruiker [&#128279;](user-roles.md) voor een volledige verdeling van wat elke rol kan doen.

## Hebben beheerders een hiërarchie? Kan één beheerder een andere met voeten treden? {#admin-hierarchy}

Nee. Teams in Experience Rollouts hebben een platte structuur. Alle leden met de **Admin** rol hebben gelijke toestemmingen en kunnen elkaars configuraties beheren. Er is geen hiërarchische goedkeuringswerkstroom tussen beheerders.

## Hoe verwijder ik een lid uit mijn team? {#remove-member}

Leden worden verwijderd via het toegangsbeheersysteem. Als Admin, onderzoek naar het toegangsverslag van het lid voor uw team en herhaal hun rol. Als u niet zeker weet hoe u dit moet doen, neemt u contact op met het team voor toegangsbeheer van uw organisatie.

## Kan een lid meer dan één rol hebben? {#multiple-roles}

Ja. Wijs meerdere rollen toe aan een lid wanneer hun verantwoordelijkheden zich uitstrekken over meer dan één functie. Bijvoorbeeld, zou een teamlid dat zowel het team beheert als eigenschapvlaggen leidt zowel **Admin** en **de Eigenaar van de Versie van het Product** rollen moeten hebben.

## Zie ook {#see-also}

* [Gebruikersrollen](user-roles.md)
* [Leden aan uw team toevoegen](add-team-members.md)
* [Teams beheren](manage-teams.md)
