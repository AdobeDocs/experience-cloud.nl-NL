---
title: De werkstroom van begin tot einde opheffen
description: Leer de end-to-end workflow voor het beheren van een gecoördineerde release in Adobe Experience Rollouts, van het definiëren van functiemarkeringen tot live gaan.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 1%

---


# De werkstroom van begin tot einde opheffen {#release-workflow}

Deze pagina beschrijft de volledige opeenvolging van activiteiten betrokken bij een gecoördineerde versie die door een Manager van de Versie wordt beheerd.

## &#x200B;1. Functiemarkeringen definiëren per toepassing {#define-flags}

Elk productteam wijst de Eigenaar van de Versie van het a **Product** toe die aan de console van de Rollouts van de Ervaring het programma opent en eigenschapvlaggen voor de toepassingen leidt zij hebben. Het productteam voert dan de voorwaardelijke logica in hun code uit, die eigenschappen achter deze vlaggen plaatsen.

## &#x200B;2. De release maken {#create-release}

Voor het maken van een nieuwe release is een supportverzoek vereist. Dit is niet volledig zelf-gediend. De steun van Rollouts van de Ervaring van het contact om de versie te hebben gecreeerd. Geef de releasenaam, het team dat eigenaar is, de doelomgeving, het doel, de deelnemende toepassingen en de verwachte duur op.

Zodra de versie wordt bevestigd, opent de Manager van de Versie de console en voltooit de versieconfiguratie.

## &#x200B;3. Functiemarkeringen toevoegen aan de release {#add-flags}

Voor elke toepassing die aan de release wordt toegevoegd, meldt de eigenaar van de productrelease van de toepassing zich aan en voegt hij de relevante functiemarkeringen toe aan de release. Deze markeringen geven de functies aan die live gaan met de release.

## &#x200B;4. Het publiek configureren {#configure-audience}

De manager van de Versie selecteert het publiek voor de versie - bijvoorbeeld, 1% van gebruikers in een specifiek land, alle gebruikers met een specifiek e-maildomein, of een lijst van specifieke gebruikers IDs. Zodra gevormd, bewaart de Manager van de Versie en publiceert de versie, die het voor het gespecificeerde publiek levend duwt.

## &#x200B;5. De rollout uitbreiden en beheren {#expand}

Nadat de versie levend gaat, kan de Manager van de Versie de publieksregels aanpassen om de rollout geleidelijk uit te breiden, voor kwesties te controleren, en de controles van de versiestatus te gebruiken om de levenscyclus te beheren. Zie [&#x200B; de staten van de Versie &#x200B;](release-states.md) voor details.

## Belangrijkste punten {#key-points}

* Alle deelnemende toepassingen stellen hun code aan productie onafhankelijk achter eigenschapmarkeringen op — geen gecoördineerde plaatsingstijdstip wordt vereist.
* De versie is het enige punt van controle dat alle vlaggen over teams gelijktijdig activeert.
* Doelgerichtheid van het publiek voor releases is gebaseerd op kenmerken van het verificatietoken (land, e-mail, gebruikers-id, percentage).

## Zie ook {#see-also}

* [Release aanvragen](request-a-release.md)
* [Regels voor het publiek van de release bijwerken](update-release-audience-rules.md)
* [Releasestatus](release-states.md)
