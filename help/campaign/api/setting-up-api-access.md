---
title: API-toegang instellen
description: Leer hoe u toegang tot Campaign Standard-API's instelt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 3e7af8a9ba41ab54738fff2f69388595041a8574
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 30%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in [Adobe Developer-documentatie](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Certificaten beheren in [Adobe Developer](https://developer.adobe.com/), zorg ervoor dat u **Systeembeheerder** rechten van de organisatie of [ontwikkelingsaccount](https://helpx.adobe.com/nl/enterprise/using/manage-developers.html) in de Admin Console.

1. **Controleer of u een digitaal certificaat hebt**, of maak er zo nodig een. De bij het certificaat geleverde openbare en privésleutels zijn nodig bij de volgende stappen.
1. **Een nieuwe integratie met Adobe Campaign Service maken** in [Adobe Developer](https://developer.adobe.com/) en configureren. Uw referenties worden dan gegenereerd (API-sleutel, klantgeheim...).
1. **Maak een JSON-webtoken (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw privésleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die door de Adobe nodig zijn om uw identiteit te verifiëren en u toegang tot de API te verlenen.

   >[!IMPORTANT]
   >
   >JWT (JSON Web Tokens) wordt momenteel uitgefaseerd en wordt vervangen door OAuth. De overgang wordt geleidelijk uitgevoerd in de komende releases van Campagne. De referenties van de serviceaccount (JWT) zijn gemarkeerd als afgekeurd. Ze blijven werken tot 27 januari 2025. Daarom moet u uw toepassing of integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 27 jan. 2025 te gebruiken. OAuth-verificatie verdient de voorkeur. U zult alle elementen vinden om van authentificatie JWT aan authentificatie OAuth op deze pagina&#39;s te migreren:
   >* [Migratie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [Implementatie](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [Veelgestelde vragen over Deprectie JWT](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

1. **Uitwisseling uw JWT voor een Token van de Toegang** via een verzoek van de POST. Deze toegangstoken moet worden gebruikt in elke header van uw API-verzoeken.

Om een veilige Adobe I/O API-sessie tussen services tot stand te brengen moet elk verzoek aan een Adobe-service de onderstaande informatie bevatten in de autorisatieheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Dit is uw persoonlijke ORGANISATIE-ID, één ORGANISATIE-ID wordt per Adobe opgegeven voor elk van uw gevallen:

   * &lt;organization> : uw productie-instantie,
   * &lt;organization-mkt-stage>: uw werkgebiedinstantie.

  Voor het verkrijgen van uw ORGANISATIE-ID-waarde raadpleegt u uw beheerder of uw technische contactpersoon bij Adobe. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer-documentatie</a>).

* **&lt;access_token>**: Uw persoonlijke toegangstoken, die werd teruggewonnen toen het ruilen van uw Token van het Web JSON door een verzoek van de POST.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

  ![alt-tekst](assets/tenant.png)

## Problemen oplossen

Als de volgende fout optreedt tijdens de integratie met AdobeIO:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Verwijs naar uw beheerder of uw Adobe technisch contact om te controleren of wordt de parameter CNAME correct gecreeerd.
