---
title: Waarom Campaign Standard API's gebruiken?
description: Meer informatie over Campaign Standard API's en waarom ze gebruiken.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: ef045e5d-cd02-44a0-9a1e-d468483a38d9
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Waarom Campaign Standard API&#39;s gebruiken {#why-using-campaign-standard-apis}

Adobe Campaign Standard biedt API&#39;s waarmee bestaande systemen kunnen integreren met het Campagneplatform om problemen in real-time op te lossen.

Openbare websites, zoals de aanmeldings- of uitschakelpagina, moeten verbinding maken met back-endsystemen om profielgegevens op te slaan. Ondersteunende systemen zoals Adobe Campaign hebben de flexibiliteit en kracht om profielgegevens in te voeren en er aangepaste bewerkingen op uit te voeren.

Hier volgen enkele voorbeelden:

* Prospects online registration.
* Bestaand klantenprofiel en beheer van marketingcommunicatievoorkeuren.
  <!--* Event based transactional communication triggering – order confirmation, booking Itinerary, password reset, etc.-->
* Zelfs de communicatie via e-mail over het verlaten van de winkelwagentje.

Aanbiedingspagina&#39;s voor aanmelding bieden klanten of vooruitzichten een manier om hun naam en e-mailadres te registreren. Zodra Campaign Standard de profielgegevens en voorkeuren vastlegt, kan het persoonlijke berichten verzenden op basis van de belangen van de persoon.

Ze zijn gemaakt met de volgende elementen:

1. Een registratieformulier met campagne-API-listeners.

   ![ alt tekst ](assets/apis_uc1.png)

1. Aangepaste acties die moeten worden uitgevoerd op basis van selectievakjes. Een klant die &#39;Speciale aanbiedingen per e-mail&#39; selecteert, ontvangt een andere aangepaste e-mail met een cadeaubon dan het normale registratieproces.

   ![ alt tekst ](assets/apis_uc2.png)

1. De details van een profiel kunnen worden gewijzigd nadat u op de koppeling Details bijwerken in de e-mail hebt geklikt. Hiermee wordt het profiel weergegeven op de pagina &quot;Uw profiel en voorkeursgegevens bijwerken&quot;. Om de bewerking uit te voeren, worden de profieldetails (sleutel) overgegaan tot de server van de Campagne en het profiel wordt teruggewonnen en vertegenwoordigd. Zodra het profiel op de knop &quot;Bijwerken&quot; klikt, wordt de informatie bijgewerkt naar het systeem (via een PATCH-opdracht).

   ![ alt tekst ](assets/apis_uc3.png)

Er is een verzameling aanvragen beschikbaar om u te helpen vertrouwd te maken met Campaign Standard API&#39;s-aanvragen. Deze verzameling in JSON-indeling biedt vooraf ontworpen API-aanvragen die veelvoorkomende gebruiksgevallen vertegenwoordigen.

In de onderstaande stappen wordt een stapsgewijze beschrijving van het gebruik beschreven voor het importeren en gebruiken van de verzameling om een profiel te maken in de Campaign Standard-database.

>[!NOTE]
>
>In ons voorbeeld wordt Postman gebruikt. U kunt echter uw favoriete REST-client gebruiken.

1. Download de inzameling JSON door [ hier ](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip) te klikken.

1. Open Postman, dan selecteer het **Dossier** / **de Invoer** menu.

1. Sleep het gedownloade bestand naar het venster. Vooraf ontworpen API-aanvragen worden weergegeven en kunnen worden gebruikt.

   ![ alt tekst ](assets/postman_collection.png)

1. Selecteer **Creërend een profiel** verzoek, dan werk het POST verzoek en het **kopballen** lusje met uw eigen informatie (&lt;ORGANIZATION>, &lt;API_KEY>, &lt;ACCESS_TOKEN>) bij. Raadpleeg [deze sectie](setting-up-api-access.md) voor meer informatie.

   ![ alt tekst ](assets/postman_uc1.png)

1. Vul het **Lichaam** lusje met de informatie in u aan het nieuwe profiel wilt toevoegen, dan **verzenden** knoop klikken om het verzoek uit te voeren.

   ![ alt tekst ](assets/postman_uc2.png)

1. Wanneer een object is gemaakt, wordt er een primaire sleutel (PKey) aan gekoppeld. Het is zichtbaar in de verzoekreactie, evenals andere attributen.

   ![ alt tekst ](assets/postman_uc3.png)

1. Open uw Campaign Standard-instantie en controleer vervolgens of het profiel is gemaakt, met alle informatie uit de laadbewerking.

   ![ alt tekst ](assets/postman_uc4.png)
