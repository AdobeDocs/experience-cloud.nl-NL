---
title: Geautomatiseerd rollout-concept
description: Begrijp hoe de geautomatiseerde rollouts in de Rollouts van de Ervaring van Adobe werken, met inbegrip van faseblokken, wachten blokken, en hoe het rollout plan automatisch vordert.
source-git-commit: d824d85c6701edc9be314713bb8e9624b183e2d2
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---


# Geautomatiseerd rollout-concept {#automated-rollout-concept}

Met een geautomatiseerde rollout kunt u in één keer uw volledige gefaseerde rollout-plan definiëren. In plaats van manueel het terugkeren aan de console om uw publiek voor elke fase uit te breiden, vormt u alle fasen en hun programma&#39;s vooruit en de Rollouts van de Ervaring door hen automatisch.

Geautomatiseerde rollouts worden ondersteund voor functiemarkeringen, functiegroepen en groepen met meerdere functies.

## Hoe werkt het {#how-it-works}

Een rollout plan wordt samengesteld uit **faseblokken** en **wachten blokken** die in opeenvolging worden uitgevoerd:

* **blok van de Fase** - bepaalt de publiekscriteria voor één fase van de rollout. Wanneer het plan een faseblok bereikt, wordt dat publiek het actieve publiek voor de eigenschap.
* **wacht blok** — bepaalt de pauze tussen twee faseblokken. Een wachtblok kan ofwel een relatieve duur zijn (bijvoorbeeld &quot;3 dagen wachten&quot;) of een vaste datum en tijd.

Het plan begint wanneer u de eigenschap publiceert of het voor een toekomstige datum plant. De bewegingen van Rollouts van de ervaring van één blok aan volgende automatisch volgens het programma u vormde.

## Faseblokgedrag {#phase-block-behavior}

Elk volgende faseblok wordt vooraf gevuld met het publiek van de vorige fase. Dit maakt het gemakkelijker om oplopend uitbreidende rollouts te bouwen waar elke nieuwe fase alle vroegere publieksgroepen naast nieuwe omvat.

>[!IMPORTANT]
>
>De regels van het publiek in elk faseblok zijn editable, zodat moet u ervoor zorgen om publiekscriteria van vorige fasen niet te schrappen wanneer u nieuwe degenen toevoegt. Als u het bereik van de doelgroep halverwege de implementatie reduceert, kunnen gebruikers onverwacht toegang tot een functie verliezen.

## Frames van implementatieplan {#rollout-plan-states}

Zodra een rollout plan levend is, kan het in één van drie staten zijn:

| Staat | Beschrijving |
|---|---|
| **lopend** | Het plan wordt uitgevoerd. Een vooruitgangsindicator in de console toont welk faseblok momenteel actief is. Alle voltooide blokken zijn vergrendeld en kunnen niet worden bewerkt. |
| **Gepauzeerd** | Het plan staat stil. Het publiek van het laatste voltooide faseblok blijft actief. De toekomstige fase en de wachtrijblokken kunnen nog worden uitgegeven terwijl gepauzeerd. |
| **Geaborteerd** | Het plan is permanent stopgezet. Het publiek van het laatste voltooide faseblok blijft actief. Het plan mag niet verder worden bewerkt. Als u het abonnement annuleert, wordt de functie niet uitgeschakeld. Als u het abonnement niet meer wilt gebruiken, moet u de status van de functie afzonderlijk wijzigen. |

## Zie ook {#see-also}

* [Een automatische rollout maken](create-automated-rollout.md)
* [Een rollout-abonnement controleren en bewerken](monitor-edit-rollout-plan.md)
* [Een functie instellen die geleidelijk moet worden geïmplementeerd](../feature-flags/set-feature-gradual-rollout.md)
