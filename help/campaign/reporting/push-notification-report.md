---
title: Pushmeldingenrapport
description: Met het Push- bericht uit-van-de-doos rapport, leer over het succes van uw dupberichten.
level: Intermediate
audience: end-user
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# Pushmeldingenrapport{#push-notification-report}

>[!CAUTION]
>
>Houd er rekening mee dat u de metriek **[!UICONTROL Message type]** naar de tabellen moet slepen om de gegevens te splitsen op basis van de leveringstypen, in dit geval de levering van pushberichten.

Het **Push- bericht** rapport verstrekt details van marketing prestaties van dupberichten in Adobe Campaign. Dit out-of-the-box rapport helpt u begrijpen hoe de gebruikers met dupberichten, mobiele toepassingen en leveranties in wisselwerking staan.

![](assets/dynamic_report_push.png)

Elke tabel wordt aangegeven met een overzichtsnummer en een overzicht van de diagrammen. U kunt wijzigen hoe de details worden weergegeven in de respectievelijke visualisatie-instellingen.

De eerste lijst **Samenvatting van het Bericht van de Duw** is verdeeld in drie categorieën: door dag, door mobiele toepassing en door levering. Het bevat de beschikbare gegevens voor ontvankelijke reactiviteit aan de levering:

* **[!UICONTROL Processed/sent]**: Het totale aantal verzonden pushberichten.
* **[!UICONTROL Delivered]**: Het aantal pushmeldingen dat is verzonden, in verhouding tot het totale aantal verzonden pushmeldingen.
* **[!UICONTROL Impressions]**: Het aantal keren dat een pushmelding aan het apparaat is afgeleverd en ongewijzigd is gelaten in het meldingscentrum. In de meeste gevallen zou het aantal indrukkingen gelijk moeten zijn aan het geleverde getal. Dit zorgt ervoor dat het apparaat het bericht kreeg en die informatie terug naar de server terugbracht.
* **[!UICONTROL Unique impressions]**: aantal afdrukken door ontvanger.
* **[!UICONTROL Click through rate]**: percentage gebruikers dat interactie had met de pushmelding.
* **[!UICONTROL Open rate]**: percentage geopende pushberichten.

![](assets/dynamic_report_push_2.png)

De tweede lijst **het bericht van de Duw klikt &amp; opent** is verdeeld in drie categorieën: door dag, door mobiele toepassing en door levering. Het bevat de beschikbare gegevens voor ontvankelijk gedrag per levering:

* **[!UICONTROL Impressions]**: het totaal van pushberichten dat door ontvangers wordt gezien.
* **[!UICONTROL Unique impressions]**: aantal afdrukken door ontvanger.
* **[!UICONTROL Click]**: Het aantal keren dat een pushmelding aan het apparaat is afgeleverd en door de gebruiker is geklikt. De gebruiker wilde het bericht bekijken, dat dan zal worden bewogen om Open het volgen te duwen, of het sluiten.
* **[!UICONTROL Unique clicks]**: Het aantal keren dat een unieke gebruiker communiceert met de pushmelding, bijvoorbeeld wanneer hij op de melding of knop klikt.
* **[!UICONTROL Open]**: Het totale aantal pushmeldingen dat aan het apparaat is geleverd en waarop gebruikers hebben geklikt, zodat de app wordt geopend. Dit is gelijkaardig aan de Duw klikt behalve zal een Duw Open niet teweeggebracht worden als het bericht werd verworpen.
* **[!UICONTROL Unique Opens]**: Aantal ontvangers dat de levering heeft geopend.
