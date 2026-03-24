---
title: Functiemarkeringen om functies in en uit te schakelen
description: Leer hoe de eigenschapmarkeringen in de Rollouts van de Ervaring u eigenschapbeschikbaarheid controleren, gebiedsdelen beheren, en plaatsingsrisico verminderen.
source-git-commit: 1c8fd9b42d08f657b4e6b16efae86faa04d15565
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---


# Functiemarkeringen om functies in en uit te schakelen {#feature-flags}

Met functiemarkeringen kunt u toepassingsfuncties in- of uitschakelen zonder dat u code opnieuw hoeft te implementeren. Zij scheiden ook codeplaatsingen van eigenschapbeschikbaarheid - de nieuwe code kan aan productie achter een vlag worden opgesteld en worden aangezet slechts wanneer u klaar bent.

Deze praktijk vermindert het risico aanzienlijk. De ontwikkelaars kunnen met behendigheid en vertrouwen bouwen, terwijl de productteams controle over de timing en het publiek van elke eigenschapversie behouden.

## Afhankelijkheden beheren tijdens de ontwikkeling {#manage-dependencies}

De vlaggen van de eigenschap helpen gebiedsdelen beheren wanneer het testen in snelle ontwikkelingscycli. Ontwikkelaars besteden minder tijd aan het oplossen van fusieconflicten en refactoring, en meer tijd aan het leveren van eigenschappen.

Omdat de eigenschapbeschikbaarheid buiten de code wordt gecontroleerd, kunnen de veelvoudige eigenschappen parallel - zonder complexe vertakking worden ontwikkeld. Afzonderlijke functies kunnen onafhankelijk van elkaar worden vernieuwd, zonder dat dit van invloed is op andere actieve functies.

## Donkere implementaties {#dark-deployments}

Omdat laat en onbruikbaar maakt besluiten buiten codebase leven, kunt u code aan productie opstellen terwijl het houden van de eigenschap onzichtbaar aan eind - gebruikers. Dit wordt genoemd a **donkere plaatsing**.

Donkere plaatsingen laten u code veilig aan productie duwen, het in het levende milieu tegen echte omstandigheden testen, en levend gaan wanneer u kiest — niet wanneer het plaatsingsprogramma u aan dwingt.

## Geleidelijke rollout {#gradual-rollout}

Wanneer u bereid bent om vrij te geven, kunt u een eigenschapvlag gebruiken om a **geleidelijke uitlooppas** uit te voeren: open de eigenschap aan 1% van gebruikers, meet terugkoppel en prestaties, dan stijgt progressief.

Deze het rollen benadering geeft u strakkere controle over de ervaring u levert en een snellere terugkoppelen lijn met echte gebruikers, zodat kunnen uw teams snel vóór een volledige versie antwoorden.

## Kill-switch {#kill-switch}

Als een versie niet zoals gepland gaat — ongunstig terugkoppelt, een insect, of een prestatieskwestie — u kunt de eigenschap van onmiddellijk het gebruiken van de eigenschapvlag als a **uitschakelen schakelaar**. Er is geen codewijziging of herplaatsing nodig.

## Levenscyclus kenmerkmarkering {#lifecycle}

Een functiemarkering in Experience Rollouts volgt deze doorsnede van de levenscyclus:

1. Een ontwikkelaar maakt een eigenschapmarkering en test deze afzonderlijk, zonder deze aan andere gebruikers bloot te stellen.
2. Een producteigenaar koppelt een publiek aan de vlag, die de eigenschap aan een bepaalde reeks externe gebruikers zichtbaar maakt.
3. De vlag wordt optioneel toegevoegd aan a [&#x200B; eigenschapgroep &#x200B;](feature-groups-to-control-multiple-features.md) om naast verwante vlaggen te worden geleid.
4. De vlag wordt optioneel toegevoegd aan a [&#x200B; versie &#x200B;](release-management.md) voor dwars-teamcoördinatie.
