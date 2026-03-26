---
title: Problemen oplossen
description: Gebruik de werkbank Rollouts van de Ervaring om de kwesties van de de evaluatie van de eigenschapvlag voor specifieke gebruikers te diagnostiseren, met inbegrip van het controleren van welke eigenschappen toegelaten, gehandicapt, of onovertroffen voor een bepaalde gebruikersidentiteit zijn.
exl-id: d64e9573-8e18-46a1-a75a-5ae5bfc7c82d
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 0%

---

# Problemen oplossen {#troubleshooting}

De Rollouts van de ervaring omvat een ingebouwd kenmerkend hulpmiddel genoemd de **Werkbank van Eigenschappen** die u helpt precies begrijpen welke eigenschapmarkeringen een specifieke gebruiker ontvangt en waarom. Gebruik dit effect om rapporten met onverwacht gedrag van functies te onderzoeken zonder problemen in code te moeten reproduceren.

## Toegang tot de functies Workbench {#access-workbench}

Voer de volgende stappen uit om de Workbench-functies te openen:

1. Meld u aan bij de Experience Rollouts-console.
2. Navigeer aan **Workbench > Eind-Gebruikers** van het hoogste menu.
3. Selecteer de **Eigenschappen** tabel.

## Een gebruikersidentiteit invoeren {#input-identity}

Om de evaluaties van de eigenschapmarkering voor een specifieke gebruiker op te zoeken, ga de volgende informatie in de werkbankvorm in:

* **type van identiteitskaart** - selecteer het type van herkenningsteken u gebruikt. Tot de ondersteunde typen behoren e-mail, GUID en de bezoeker-id. U kunt de vlag van de a **versie** ook ingaan direct om op te zoeken welke versies voor een gebruiker werden toegelaten die op hun vlagwaarde wordt gebaseerd.
* **waarde van identiteitskaart** - ga het herkenningsteken van de gebruiker in. Als u e-mail als type identiteitskaart selecteert, merk op dat veelvoudige GUIDs met het zelfde e-mailadres kan worden geassocieerd. Een GUID dropdown wordt verstrekt zodat kunt u tussen bijbehorende GUIDs schakelen.
* **Bron van de Auth type** - Uitgezocht indien van toepassing op uw integratie.
* **variabelen van de Context** - naar keuze verstrekt context zeer belangrijke-waardeparen die de evaluatie van de publieksregel (bijvoorbeeld, land, apparatentype) beïnvloeden.
* **Team en toepassing** - selecteer het team en de toepassing waarvoor u eigenschapvlaggen wilt halen. Uw huidige team en een van de toepassingen zijn standaard vooraf geselecteerd.

Na het invullen van de vorm, uitgezochte **Eigenschappen van de Vetch**.

## De resultaten interpreteren {#interpret-results}

De resultaten zijn afhankelijk van het ingevoerde id-type.

### Opzoeken via e-mail of GUID {#email-guid-lookup}

Wanneer u omhoog een gebruiker door e-mail of GUID kijkt, verschijnen twee secties in de resultaten:

**de vlaggen van de Versie**

Deze sectie toont drie lijsten voor het geselecteerde team en de toepassing:

* **Toegelaten** — Versies momenteel actief voor deze gebruiker.
* **Gehandicapten** — Versies die bestaan maar niet voor deze gebruiker worden toegelaten.
* **Ongebruikte** — De beetjes van de Versie die geen versie in bijlage aan hen hebben.

De versies verbonden aan het momenteel geselecteerde team en de toepassing verschijnen bij de bovenkant van elke lijst.

{de vlaggen en de groepen van de Eigenschap 0} ****

Deze sectie bevat een lijst met alle functiemarkeringen van het geselecteerde team en de geselecteerde toepassing die momenteel zijn ingeschakeld voor de gebruiker. Elk item toont:

* Functiemarkering en naam
* Functiegroep (als de vlag tot één behoort)
* Variant (als A/B-tests zijn geconfigureerd)
* Of de markering is gekoppeld aan het publiek

U kunt **ook selecteren toont Verzoek/Reactie** om het nauwkeurige API verzoek en de reactie te inspecteren die de resultaten produceerden.

### Niet-eigen e-mail- of niet-GUID-id {#non-self-lookup}

Wanneer de ingegane e-mail niet uw is, of wanneer een niet-GUID type van identiteitskaart wordt gebruikt, slechts worden de **vlaggen van de Eigenschap en de groepen** sectie getoond.

### Opzoekopdracht vrijgavemarkering {#release-flag-lookup}

Wanneer u de vlag van de a **versie** als type van identiteitskaart ingaat, slechts wordt de **vlaggen van de Versie** sectie getoond, die de versies werden toegelaten en voor de gebruiker onbruikbaar gemaakt verbonden aan die vlag.

## Algemene kwesties {#common-issues}

De volgende lijst beschrijft gemeenschappelijke problemen en hoe te om hen te onderzoeken gebruikend de werkbank.

| Symptoom | Te controleren wat |
|---|---|
| Gebruiker ontvangt geen functiemarkering die hij of zij nodig heeft | Verifieer het team en de toepassingsselectie. Controleer of de id van de gebruiker overeenkomt met het type publieksregel (e-mail, GUID, enz.). Bevestig de eigenschap in **publiceer** of **Volledige staat van de Uitvoer** is. |
| Functie is onverwacht ingeschakeld voor alle gebruikers | Bevestig dat op de functie geen publieksregels zijn toegepast of dat het percentage is ingesteld op 100%. Controle als de eigenschap in **Volledige staat van de Uitvoer** is. |
| De regel van het publiek komt niet overeen | Gebruik de werkbank met contextvariabelen om te bevestigen dat de waarden die bij runtime worden overgegaan aanpassen wat in de publieksregel wordt gevormd. |
| De vlagstaat van de eigenschap is correct maar de gebruiker ziet nog oud gedrag | Controleer TTL voor de toepassing wordt gevormd die. De de eigenschapgegevens en verfrist slechts van de geheime voorgeheugens van SDK bij het gevormde opiniepeilingsinterval. |

## Zie ook {#see-also}

* [Ondersteuning](get-support.md)
* [Contact opnemen met ondersteuning](contact-support.md)
