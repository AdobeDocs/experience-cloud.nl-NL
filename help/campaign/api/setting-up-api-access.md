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
source-git-commit: 18979fea28f4f3adce1139293203a59876831313
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 27%

---

# API-toegang instellen {#setting-up-api-access}

Adobe Campaign Standard API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd in de [ documentatie van Adobe Developer ](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om certificaten in [ Adobe Developer ](https://developer.adobe.com/) te beheren, zorg ervoor u **de beheerderrechten van het Systeem** op de organisatie of a [ ontwikkelaarrekening ](https://helpx.adobe.com/nl/enterprise/using/manage-developers.html) in de Admin Console hebt.

1. **Controleer of u een digitaal certificaat hebt**, of maak er zo nodig een. De bij het certificaat geleverde openbare en privésleutels zijn nodig bij de volgende stappen.
1. **creeer een nieuwe integratie aan de Dienst van Adobe Campaign** in [ Adobe Developer ](https://developer.adobe.com/) en vorm het. Uw referenties worden dan gegenereerd (API-sleutel, klantgeheim...).
1. **creeer een OAuth Server-aan-Server** credential door deze [ implementatiestappen te volgen ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)

   >[!IMPORTANT]
   >
   >JWT (JSON Web Tokens) wordt momenteel uitgefaseerd en wordt vervangen door OAuth. De overgang wordt geleidelijk uitgevoerd in de komende releases van Campagne. De referenties van de serviceaccount (JWT) zijn gemarkeerd als afgekeurd. Ze blijven werken tot 27 januari 2025. Daarom moet u uw toepassing of integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 27 jan. 2025 te gebruiken. OAuth-verificatie verdient de voorkeur. U zult alle elementen vinden om van authentificatie JWT aan authentificatie OAuth op deze pagina&#39;s te migreren:
   >* [ Migratie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)
   >* [ Implementatie ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)
   >* [ Veelgestelde Veelgestelde vragen van de Verdringing JWT ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)

Om een veilige Adobe I/O API-sessie tussen services tot stand te brengen moet elk verzoek aan een Adobe-service de onderstaande informatie bevatten in de autorisatieheader.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZATION>**: Dit is uw persoonlijke ORGANIZATION identiteitskaart, wordt één ORGANIZATION identiteitskaart verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANIZATION>: uw productieexemplaar
   * &lt;ORGANIZATION-market-stage>: de instantie van het werkgebied.

  Voor het verkrijgen van uw ORGANISATIE-ID-waarde raadpleegt u uw beheerder of uw technische contactpersoon bij Adobe. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie de <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/"> documentatie van Adobe Developer </a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw Symbolisch van het Web JSON door een verzoek van de POST.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de Dienst van Adobe Campaign.

  ![ alt tekst ](assets/tenant.png)

## Problemen oplossen

Als de volgende fout optreedt tijdens de integratie met AdobeIO:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Verwijs naar uw beheerder of uw Adobe technisch contact om te controleren of wordt de parameter CNAME correct gecreeerd.
