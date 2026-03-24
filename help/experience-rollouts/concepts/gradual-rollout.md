---
title: Geleidelijke rollout
description: Leer hoe u dankzij de geleidelijke rollouts in de Experience de levering veilig kunt uitvoeren, met real-time feedback en minimaal risico.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---


# Geleidelijke rollout {#gradual-rollout}

Met een geleidelijke implementatie wordt een nieuwe functie stapsgewijs in productie genomen en niet voor alle gebruikers tegelijk. Deze benadering vermindert risico&#39;s, helpt backend lading te beheren, en leidt tot een strakke terugkoppelen lijn alvorens volledige versie.

## Voordelen {#benefits}

**het net van de Veiligheid**
Door eerst aan een klein publiek vrij te geven, kunt u terugkoppelen volgen en gedrag in productie controleren alvorens zich uit te breiden. Als er problemen optreden, is de impact beperkt en kan de functie onmiddellijk worden uitgeschakeld, zonder dat de code wordt gewijzigd of opnieuw wordt geïmplementeerd.

**het beheer van de achterste lading**
Als een functie gelijktijdig voor alle gebruikers wordt geopend, kunnen er plotselinge pieken optreden bij het laden van de server. Een geleidelijke uitrol verdeelt de toename van verkeer in tijd, toestaand infrastructuur om regelmatig te schrapen.

**in real time terugkoppelen**
Elke fase van de rollout oppervlakken geeft feedback van echte gebruikers. Teams kunnen op die feedback reageren — de ervaring verfijnen, randgevallen corrigeren of berichten aanpassen — vóór de volgende fase.

## Hoe werkt het {#how-it-works}

De Rollouts van de ervaring verstrekt korrelige het richten regels om de blootstelling van de gebruiker stap voor stap te verhogen. Dit patroon kan standaard geleidelijk worden uitgevoerd:

1. Laat de eigenschap voor **1%** van gebruikers toe
2. Feedback en prestatiemetingen bewaken
3. Breid aan **uit 10%**, toen **25%**, toen **50%**
4. Bereik **100%** zodra het vertrouwen wordt gevestigd

Bij elke stap kan een enkele actie de rollout pauzeren of de functie volledig uitschakelen als er iets verkeerd gaat.

## Zie ook {#see-also}

* [Functiemarkeringen om functies in en uit te schakelen](feature-flags-to-enable-disable-features.md)
* [Release-beheer](release-management.md)
