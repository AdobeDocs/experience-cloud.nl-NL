---
title: Waarom Campaign Standard-API's gebruiken?
description: Meer informatie over Campaign Standard-API's en waarom u deze gebruikt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: ef045e5d-cd02-44a0-9a1e-d468483a38d9
source-git-commit: 3f4400f24b75e8e435610afbe49e9d9444dbf563
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Waarom Campaign Standard-API&#39;s worden gebruikt {#why-using-campaign-standard-apis}

Adobe Campaign Standard biedt API&#39;s waarmee bestaande systemen kunnen integreren met het Campagneplatform om problemen in real-time op te lossen.

Openbare websites, zoals de aanmeldings- of uitschakelpagina, moeten verbinding maken met back-endsystemen om profielgegevens op te slaan. Ondersteunende systemen zoals Adobe Campaign hebben de flexibiliteit en kracht om profielgegevens in te voeren en er aangepaste bewerkingen op uit te voeren.

Hier volgen enkele voorbeelden:

* Prospects online registration.
* Bestaand klantenprofiel en beheer van marketingcommunicatievoorkeuren.
* Transactiecommunicatie op basis van gebeurtenissen activeren - orderbevestiging, boekingsroute, opnieuw instellen van wachtwoord, enz.
* Zelfs de communicatie via e-mail over het verlaten van de winkelwagentje.

Aanbiedingspagina&#39;s voor aanmelding bieden klanten of vooruitzichten een manier om hun naam en e-mailadres te registreren. Zodra het Campaign Standard de profielinformatie en voorkeur vangt, kan het gepersonaliseerde berichten verzenden die op de belangen van de persoon worden gebaseerd.

Ze zijn gemaakt met de volgende elementen:

1. Een registratieformulier met campagne-API-listeners.

   ![alt-tekst](assets/apis_uc1.png)

1. Aangepaste acties die moeten worden uitgevoerd op basis van selectievakjes. Een klant die &#39;Speciale aanbiedingen per e-mail&#39; selecteert, ontvangt een andere aangepaste e-mail met een cadeaubon dan het normale registratieproces.

   ![alt-tekst](assets/apis_uc2.png)

1. De details van een profiel kunnen worden gewijzigd nadat u op de koppeling Details bijwerken in de e-mail hebt geklikt. Hiermee wordt het profiel weergegeven op de pagina &quot;Uw profiel en voorkeursgegevens bijwerken&quot;. Om de bewerking uit te voeren, worden de profieldetails (sleutel) overgegaan tot de server van de Campagne en het profiel wordt teruggewonnen en vertegenwoordigd. Nadat het profiel op de knop &quot;Bijwerken&quot; heeft geklikt, wordt de informatie in het systeem bijgewerkt (via de opdracht PATCH).

   ![alt-tekst](assets/apis_uc3.png)

Er is een verzameling aanvragen beschikbaar om u te helpen vertrouwd te maken met Campaign Standard-API&#39;s. Deze verzameling in JSON-indeling biedt vooraf ontworpen API-aanvragen die veelvoorkomende gebruiksgevallen vertegenwoordigen.

In de onderstaande stappen wordt een stapsgewijze beschrijving van het gebruik beschreven voor het importeren en gebruiken van de verzameling om een profiel te maken in een database van Campaigns Standard.

>[!NOTE]
>
>In ons voorbeeld wordt Postman gebruikt. U kunt echter uw favoriete REST-client gebruiken.

1. Download de JSON-verzameling door op [hier](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Open Postman en selecteer vervolgens de **Bestand** / **Importeren** -menu.

1. Sleep het gedownloade bestand naar het venster. Vooraf ontworpen API-aanvragen worden weergegeven en kunnen worden gebruikt.

   ![alt-tekst](assets/postman_collection.png)

1. Selecteer de **Een profiel maken** verzoek, dan update het verzoek van de POST en **Kopteksten** met uw eigen gegevens (&lt;organization>, &lt;api_key>, &lt;access_token>). Raadpleeg [deze sectie](setting-up-api-access.md) voor meer informatie.

   ![alt-tekst](assets/postman_uc1.png)

1. Vul de **Lichaam** met de informatie die u aan het nieuwe profiel wilt toevoegen, klikt u op de knop **Verzenden** om de aanvraag uit te voeren.

   ![alt-tekst](assets/postman_uc2.png)

1. Wanneer een object is gemaakt, wordt er een primaire sleutel (PKey) aan gekoppeld. Het is zichtbaar in de verzoekreactie, evenals andere attributen.

   ![alt-tekst](assets/postman_uc3.png)

1. Open uw instantie van het Campaign Standard, dan controleer dat het profiel, met alle informatie van de lading wordt gecreeerd.

   ![alt-tekst](assets/postman_uc4.png)
