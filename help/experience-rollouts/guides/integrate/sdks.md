---
title: SDK's
description: Leer meer over de SDK-architectuur in Adobe Experience Rollouts en de beschikbare Mobile SDK-extensie voor Android.
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# SDK&#39;s {#sdks}

Experience Rollouts biedt SDK&#39;s voor het integreren van functiemarkeringen in uw toepassingen. Op deze pagina vindt u een beschrijving van de SDK-architectuur en de beschikbare opties.

## SDK-architectuur {#architecture}

Alle Experience Rollouts SDK&#39;s hebben dezelfde kernarchitectuur:

* **Initialisatie** — SDK wordt gevormd bij opstarten en registreert met de dienst van Rollouts van de Ervaring.
* **herwinning van de Eigenschap** — SDK wint eigenschapvlaggegevens terug en evalueert lokale vlaggen.
* **Caching** - de de eigenschapvlaggegevens van de geheime voorgeheugens van SDK en verfrist het op een configureerbaar opiniepeilingsinterval (TTL).
* **de behandeling van de Fout** — Als de dienst niet beschikbaar is, gaat SDK het dienen van de evaluaties van de eigenschapvlag van het lokale geheime voorgeheugen voort.

## Beschikbare SDK&#39;s {#available-sdks}

### Android-extensie {#android-extension}

De Experience Rollout-extensie voor Android kan worden geïntegreerd met de Adobe Experience Platform Mobile SDK.

Zie de [ handleiding van de de uitbreidingsintegratie van Android ](../sdk-releases/android/android-extension-integration-guide.md) voor opstellingsinstructies.

>[!NOTE]
>
>Er worden extra SDK-opties voor internet en andere mobiele platforms voorbereid en deze zullen binnenkort beschikbaar zijn. Neem contact op met uw Adobe-vertegenwoordiger voor hulp bij vroege toegang.

## Zie ook {#see-also}

* [Android-integratiegids](../sdk-releases/android/android-extension-integration-guide.md)
* [Webservices](web-services.md)
* [Integratiestappen](integration-steps.md)
