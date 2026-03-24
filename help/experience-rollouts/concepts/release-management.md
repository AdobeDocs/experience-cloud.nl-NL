---
title: Beheer vrijgeven in Experience Rollouts
description: Leer hoe releasebeheer in Experience Rollouts de levering van multiteamfuncties coördineert via donkere implementaties, productietests en geleidelijke rollouts.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Beheer vrijgeven in Experience Rollouts {#release-management}

Een typische belangrijke versie impliceert veelvoudige teams en veelvoudige toepassingen, elk met hun eigen plaatsingschronologie en gebiedsdelen. De Rollouts van de ervaring verstrekt een model van het versiebeheer dat teams laat onafhankelijk werken terwijl nog het leveren van een gecoördineerde, gecontroleerde versie aan eind - gebruikers.

## Belangrijkste mogelijkheden {#capabilities}

### Donkere implementaties {#dark-deployments}

Teams hoeven hun code-implementatie niet langer te onderbrengen met een specifieke go-live datum. De code kan aan productie achter eigenschapvlaggen op elk ogenblik worden opgesteld. Eindgebruikers zien geen wijzigingen voordat de release wordt geactiveerd. Teams kunnen in hun eigen tempo implementeren, waarbij ze erop vertrouwen dat niets voortijdig wordt belicht.

### Testen in productie {#testing-in-production}

Zodra de code aan productie wordt opgesteld — donker opgesteld — De Rollouts van de Ervaring kunnen de eigenschappen voor interne meetapparaten en teams QA openen. Dit maakt het mogelijk volledig te testen op de productieomgeving en op de werkelijke productiegegevens, zonder dat het risico bestaat dat veranderingen aan eindgebruikers worden blootgesteld.

### Geleidelijke rollout {#gradual-rollout}

Als een release klaar is om live te gaan, hoeft deze niet helemaal niets te zijn. Dankzij Experience Rollouts kunt u de rollout progressief beheren, te beginnen met een klein percentage gebruikers, feedback en prestaties te controleren en het publiek in de loop der tijd uit te breiden. Dit vermindert de belasting van back-endsystemen en geeft teams de tijd om op problemen te reageren voordat ze volledig worden belicht.

### Gecoördineerde activering {#coordinated-activation}

De veelvoudige teams ontwikkelen eigenschappen onafhankelijk, elk achter hun eigen eigenschapvlaggen. Zodra alle teams klaar zijn, verstrekt de Rollouts van de Ervaring één enkel controlepunt om alle vlaggen over teams en toepassingen gelijktijdig — of geleidelijk — te activeren zodat gaat de versie als één samenhangende ervaring leven.

## Zie ook {#see-also}

* [Begrip van releasebeheer](concept-of-release-management.md)
* [Functiegroepen om meerdere functies te beheren](feature-groups-to-control-multiple-features.md)
* [Geleidelijke rollout](gradual-rollout.md)
