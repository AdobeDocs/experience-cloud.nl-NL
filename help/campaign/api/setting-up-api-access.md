---
title: API-toegang instellen
description: Leer hoe u toegang tot Campaign Standard API's instelt.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 27%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd in de [&#x200B; documentatie van Adobe Developer &#x200B;](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om certificaten in [&#x200B; Adobe Developer &#x200B;](https://developer.adobe.com/) te beheren, zorg ervoor u **de beheerderrechten van het Systeem** op de organisatie of a [&#x200B; ontwikkelaarrekening &#x200B;](https://helpx.adobe.com/nl/enterprise/using/manage-developers.html) in Admin Console hebt.

1. **Controleer of u een digitaal certificaat hebt**, of maak er zo nodig een. De bij het certificaat geleverde openbare en privésleutels zijn nodig bij de volgende stappen.
1. **creeer een nieuwe integratie aan de Dienst van Adobe Campaign** in [&#x200B; Adobe Developer &#x200B;](https://developer.adobe.com/) en vorm het. Uw referenties worden dan gegenereerd (API-sleutel, klantgeheim...).
1. **creeer een OAuth Server-aan-Server** credential door deze [&#x200B; implementatiestappen te volgen &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)

   >[!IMPORTANT]
   >
   >JWT (JSON Web Tokens) wordt momenteel uitgefaseerd en wordt vervangen door OAuth. De overgang wordt geleidelijk uitgevoerd in de komende releases van Campagne. De referenties van de serviceaccount (JWT) zijn gemarkeerd als afgekeurd. Ze blijven werken tot 27 januari 2025. Daarom moet u uw toepassing of integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 27 jan. 2025 te gebruiken. OAuth-verificatie verdient de voorkeur. U zult alle elementen vinden om van authentificatie JWT aan authentificatie OAuth op deze pagina&#39;s te migreren:
   >* [&#x200B; Migratie &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [&#x200B; Implementatie &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [&#x200B; Veelgestelde Veelgestelde vragen van de Verdringing JWT &#x200B;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

Om een veilige Adobe I/O API-sessie tussen services tot stand te brengen moet elk verzoek aan een Adobe-service de onderstaande informatie bevatten in de autorisatieheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>**: Dit is uw persoonlijke ORGANIZATION identiteitskaart, één ORGANIZATION identiteitskaart wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANIZATION>: uw productieexemplaar
   * &lt;ORGANIZATION-market-stage>: de instantie van het werkgebied.

  Voor het verkrijgen van uw ORGANISATIE-ID-waarde raadpleegt u uw beheerder of uw technische contactpersoon bij Adobe. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie de <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/"> documentatie van Adobe Developer </a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Tken van het Web JSON door een POST verzoek.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

  ![&#x200B; alt tekst &#x200B;](assets/tenant.png)

## Problemen oplossen

Als de volgende fout optreedt tijdens de integratie met AdobeIO:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Raadpleeg uw beheerder of uw technische contactpersoon voor Adobe om te controleren of de CNAME-parameter correct is gemaakt.
