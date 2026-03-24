---
title: Releasestatus
description: Leer meer over de levenscyclusstaten van een release in Adobe Experience Rollouts, inclusief wat elke status betekent en welke overgangen zijn toegestaan.
source-git-commit: ae420329b94b24fcd173734b414aecf1c5fc16ca
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 2%

---


# Releasestatus {#release-states}

Een Manager van de Versie kan de staat van een versie van de consolenavigatie direct bijwerken. De status bepaalt of de release live is, beperkt is tot testen, volledig is geïmplementeerd of gesloten.

## Beschikbare statussen {#states}

| # | Staat | Beschrijving | Toegestane wijzigingen |
|---|---|---|---|
| 1 | **Ontwerp** | De release wordt opgeslagen in het systeem, maar nog niet actief. Er worden geen publieksregels toegepast. | Alle toegestane wijzigingen (release, functies, publiek). |
| 2 | **Bewaarde** | De release wordt geregistreerd en er wordt een slot aan toegewezen. De release is nog niet zichtbaar voor gebruikers. | Alle toegestane wijzigingen. |
| 3 | **Gepubliceerd** | De release is live voor het opgegeven publiek. Gebruikers die aan de publiekscriteria voldoen, ontvangen de functies. | Alle toegestane wijzigingen. |
| 4 | **Volledige rollout** | De release is beschikbaar voor alle gebruikers, ongeacht de publieksregels. Alle publieksregels worden verwijderd. | Functiewijzigingen toegestaan. Het publiek kan niet worden gewijzigd. |
| 5 | **Baselined** | Alle gebruikers hebben nu de functies van deze release als standaardgedrag. De voorwaardelijke code kan worden verwijderd. De sleuf voor de release wordt vrijgemaakt. | Geen wijzigingen toegestaan. |
| 6 | **Geaborteerd** | De release is gestopt. Geen enkele gebruiker ontvangt functies uit deze release. De sleuf voor de release wordt vrijgemaakt. | Geen wijzigingen toegestaan. |

## Toegestane overgangen {#transitions}

Niet alle frameovergangen zijn toegestaan. Als u de toegestane paden begrijpt, kunt u uw rollout plannen en fouten bij het beheren van statuswijzigingen voorkomen:

* Een release kan door de statussen heen: Concept → Saved → Published → Full rollout → Baselined
* Een versie kan worden afgebroken uit concept, opgeslagen, gepubliceerd of volledig rollout
* Als Baselined of Afgebroken is, zijn geen verdere wijzigingen meer toegestaan

## Vrijgavecapaciteit {#capacity}

Het aantal actieve (Opgeslagen of Gepubliceerde) releases is op elk moment beperkt. Capaciteit vrijmaken:

* De beweging voltooide versies aan **Baselined** zodra alle deelnemende toepassingen hun voorwaardelijke code hebben verwijderd.
* **verlaat** versies die niet succesvol waren en niet zullen worden voortgezet.

Plan de basislijn of abort uw releases binnen drie maanden.

## Zie ook {#see-also}

* [Release aanvragen](request-a-release.md)
* [De werkstroom van begin tot einde opheffen](release-workflow-end-to-end.md)
* [Regels voor het publiek van de release bijwerken](update-release-audience-rules.md)
