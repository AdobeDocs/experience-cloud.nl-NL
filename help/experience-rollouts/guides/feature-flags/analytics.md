---
title: Analyse
description: Leer hoe u het ingebouwde analytische dashboard in Adobe Experience Rollouts inschakelt en gebruikt om de prestaties van de functiemarkering te volgen en de invloed van de rollout te meten.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---


# Analyse {#analytics}

Experience Rollouts biedt ingebouwde analyses voor functiemarkeringen, functiegroepen, groepen met meerdere teams functies en releases. Gebruik het analytische dashboard om te begrijpen hoeveel gebruikers deelnemen aan de rollout en hoe de variant- en besturingsgroepen met elkaar vergelijken.

## Analyses inschakelen {#enable}

Analyses moeten op twee niveaus worden ingeschakeld:

1. **het niveau van de Toepassing** — De steun van Rollouts van de Ervaring van het Contact om analyses voor uw toepassing toe te laten.
2. **de vlagniveau van de Eigenschap** - Zodra de analyse voor uw toepassing wordt toegelaten, controleer **analytische** checkbox op het **BasisDetails** lusje van elke eigenschapvlag u wilt volgen.

>[!NOTE]
>
>Analytics kan standaard worden ingeschakeld voor maximaal 20 functiemarkeringen per toepassing. Neem contact op met de ondersteuningsafdeling als u deze limiet wilt verhogen.

## Het dashboard Analytics weergeven {#dashboard}

Als analyses eenmaal zijn ingeschakeld, worden gegevens bijgehouden met vlaggen van alle functies, groepen van functies en releases voor uw toepassing. Heb toegang tot het dashboard door **Resultaten** op de eigenschapvlag, eigenschapgroep, of versie te selecteren u wilt analyseren.

Het dashboard wordt weergegeven:

* **Deelnemers** — Totaal aantal gebruikers die voor de eigenschap (variant + gecombineerde controlegroep) gekwalificeerd
* **de groep van de Controle** — Aantal gebruikers die aan de controlegroep worden toegewezen (gebruikers die de standaardervaring ontvingen)
* **Dag-vlakke grafiek** — Dagelijkse lijngrafieken die inschrijving in de variant en controlegroep in tijd tonen; de tellers wijzen erop wanneer de configuratie van de eigenschapvlag werd bijgewerkt
* **variant-vlakke analyses** — Cumulatieve telling van gebruikers ingeschreven in de controlegroep en elke variant

Voor eigenschapgroepen en versies, selecteer **Resultaten** drop-down om een toepassing en meningsanalyse voor die toepassing te kiezen. Analytics is alleen beschikbaar voor toepassingen waarvoor deze functie is ingeschakeld.

## Zie ook {#see-also}

* [De eerste functiemarkering maken](create-your-first-feature-flag.md)
* [A/B testen met functiemarkeringen](a-b-testing.md)
* [Een functiegroep maken](create-a-feature-group.md)
