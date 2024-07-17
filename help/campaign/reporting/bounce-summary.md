---
title: Overzicht van niet-bezorging
description: Met het overzicht van de Stuiteren uit-van-de-doos rapport, leer over de status van uw verzonden campagnes en fouten zij kunnen hebben ontmoet.
audience: end-user
level: Intermediate
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: b341edad-aa82-43d8-a5a1-b33a19973a1a
source-git-commit: 34c6f8a137a9085b26c0ea8f78930cff6192cfc9
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# Overzicht van niet-bezorging{#bounce-summary}

In dit rapport worden de algemene harde en zachte fouten beschreven die tijdens de leveringen zijn opgetreden, alsmede de automatische verwerking van steunbedragen.

![](assets/campaign_reports_bounces.png)

Elke tabel wordt aangegeven met een overzichtsnummer en een overzicht van de diagrammen. U kunt wijzigen hoe de details worden weergegeven in de respectievelijke visualisatie-instellingen.

**Vloeiende 5 herverdeling** maakt een lijst van de vijf leveringen met het hoogste aantal quarantines:

De **lijst van de Bounce redenen** bevat de beschikbare gegevens voor de types van fouten die stuitingen voor elke levering veroorzaakten:

* **[!UICONTROL User unknown]**: Het type fout dat wordt gegenereerd wanneer een levering naar een ongeldig e-mailadres wordt verzonden.
* **[!UICONTROL Invalid domain]**: Het type fout dat wordt gegenereerd wanneer een levering wordt verzonden naar een e-mailadres waarvan het domein onjuist is of niet meer bestaat.
* **[!UICONTROL Unreachable]**: Het type fout dat in de tekenreeks voor het verzenden van berichten wordt aangetroffen, zoals een tijdelijk onbereikbaar domein.
* **[!UICONTROL Account disabled]**: Het type fout dat wordt gegenereerd wanneer een levering wordt verzonden naar een e-mailadres dat niet meer bestaat.
* **[!UICONTROL Mailbox full]**: Het type fout dat wordt gegenereerd wanneer het Postvak IN van de ontvanger vol is. Er zijn vijf pogingen om het bericht te leveren alvorens deze fout wordt geproduceerd.
* **[!UICONTROL Not connected]**: Het type fout dat wordt gegenereerd wanneer de mobiele telefoon van de ontvanger is uitgeschakeld of wanneer deze niet is verbonden met een netwerk op het moment dat het bericht wordt verzonden.

  >[!NOTE]
  >
  >Dit type fout heeft alleen betrekking op leveringen op mobiele kanalen.

* **[!UICONTROL Refused]**: Het type fout dat wordt gegenereerd wanneer een adres wordt geweigerd door de internetprovider (ISP). Bijvoorbeeld, wanneer een veiligheidsregel door anti-Spam software is toegepast.

De **repartitie van het Domein** lijst toont de algemene problemen die tijdens de leveringen volgens het ontvankelijke domein worden ontmoet.
