---
title: Aanbevelingen en beperkingen
description: Aanbevelingen en beperkingen bij het migreren naar de REST-API's voor Campagne v8.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
mini-toc-levels: 1
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: 45acebb1-9325-4e26-8fe9-cc73f745d801
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 1%

---

# Aanbevelingen en beperkingen {#limitations}

## Machtigingen en beveiliging {#permissions}

### Toewijzing van productprofielen

In Campaign Standard hebt u toegang gekregen tot API&#39;s met een verhoogde beheerdersrol, ongeacht het toegewezen productprofiel. Campagne v8 introduceert een andere set productprofielen, waarvoor u Campaign Standard moet toewijzen aan productprofielen voor Campaign v8.

Met de migratie worden twee productprofielen toegevoegd aan uw bestaande of vooraf gemaakte technische accounts: Beheerder en Berichtencentrum (voor toegang tot transactie-API&#39;s). Controleer de productprofieltoewijzing en wijs het vereiste productprofiel toe als u niet wilt dat het Admin-productprofiel aan uw technische account wordt toegewezen.

### Tenant-id

Na migratie, voor om het even welke toekomstige integratie, wordt het geadviseerd om uw **24 huurdersidentiteitskaart van de Campagne v8** in REST URLs te gebruiken, die uw vorige Campaign Standard huurdersidentiteitskaart vervangen.

### Sleutelgebruik

Het beheer van PKey-waarden verschilt tussen Campaign Standard en Campaign v8. Als u PKeys met Campaign Standard opslaat, zorg ervoor uw implementatie dynamisch verdere API vraag gebruikend PKeys of hrefs die uit vorige API vraag wordt verkregen vormt.

## Beschikbare API&#39;s {#deprecated}

Momenteel zijn de REST API&#39;s die hieronder worden vermeld, beschikbaar voor gebruik:

* **Profielen**
* **de Diensten &amp; abonnementen**
* **Aangepaste resources**
* **Workflows**
* **Transactionele berichten**

>[!AVAILABILITY]
>
>Voor nu, is de **Transactionele berichten** REST API niet beschikbaar.
>
>De REST API&#39;s die hieronder worden vermeld, zijn afgekeurd en zijn niet beschikbaar voor gebruik:
>* Marketinggeschiedenis
>* Organisatorische eenheden
>* Privacybeheer

## Filteren

* Als u uw filters wilt gebruiken in REST API-ladingen, moet u ze bewerken in Campagne v8 en een naam opgeven die u in uw ladingen kunt gebruiken. U doet dit door de aanvullende parameters van het filter vanaf het tabblad **[!UICONTROL Parameters]** te openen en de gewenste naam op te geven in het veld **[!UICONTROL Filter name in REST API]** .

  ![](assets/api-filtering.png)


* Het voorvoegsel &quot;by&quot; dat vereist is om aangepaste filters te gebruiken, is niet langer nodig. De filternaam moet zo worden gebruikt in uw aanvragen.

  Voorbeeld:

  `GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/<customFilterName>?<customFilterparam>=<customFilterValue>`

## Gedropte databasevelden

Sommige velden uit de database worden tijdens de migratie verwijderd. Als u een weggelaten veld gebruikt, retourneert REST API&#39;s lege waarden. In de toekomst worden alle neergezette velden vervangen en verwijderd.

## POST met gekoppelde bronnen

Wanneer het gebruiken van het volgende formaat van het verzoeklichaam, met &quot;VehicleOwner&quot;die de verbinding aan &quot;nms :recipient&quot;vertegenwoordigen:

```
{
    "vehicleNumber": "20009",
    "vehicleName": "Model E",
    "vehicleOwner":{
        "firstName":"tester 11",
        "lastName":"Smith 11"
    }
}
```

De koppelingsgegevens worden genegeerd. Bijgevolg wordt een nieuwe record gegenereerd onder &quot;cusVehicle&quot; die alleen waarden voor &quot;vehicleNumber&quot; en &quot;vehicleName&quot; bevat. Nochtans, blijft de verbinding ongeldig, resulterend in &quot;vehicleOwner&quot;die aan ongeldig wordt geplaatst.

Wanneer in Campaign v8 dezelfde structuur van de aanvraaginstantie wordt gebruikt en het &quot;voertuig&quot; aan een profiel is gekoppeld, treedt een fout op. Deze fout treedt op omdat de eigenschap &quot;firstName&quot; niet wordt herkend als geldig voor &quot;cusVehicle&quot;. Een aanvraaginstantie die alleen de kenmerken zonder de koppeling omvat, functioneert echter zonder problemen.

## PATCH-bewerkingen

* Campagne v8 biedt geen ondersteuning voor PATCH met een lege aanvraaginstantie: er wordt een 204-status Geen inhoud geretourneerd.
* Hoewel Campaign Standard PATCH op elementen/kenmerken in een schema ondersteunt, worden PATCH-bewerkingen op locatie niet ondersteund in Campagne v8. Als u een PATCH probeert te activeren op een locatie, wordt een 500 Interne serverfout gegenereerd met een foutbericht dat aangeeft dat de eigenschap &#39;zipCode&#39; niet geldig is voor de bron &#39;profile&#39;.

## REST-reacties

In de onderstaande sectie worden kleine verschillen tussen Campaign Standard en v8 REST-antwoorden weergegeven.

* Voor enkele GET-records bevat de reactie de href in de reactie.
* Wanneer hierom wordt gevraagd met het kenmerk, biedt Campagne v8 Aantal en Paginering in de reactie.
* Na POST-bewerkingen worden waarden van gekoppelde bronnen geretourneerd in de reactie.

## Foutcodes en berichten

In de onderstaande sectie ziet u de verschillen tussen foutcodes en berichten van Campaign Standard en Campagne v8.

| Scenario | Campaign Standard | Campaign v8 |
|  ---  |  ---  |  ---  |
| Een ongeldige PKey in request Body gebruiken | 500 - het attribuut &quot;O5iRp40EGA&quot;onbekend (zie definitie van &quot;Profielen (nms :recipient)&quot;schema). XTK-170036 Kan expressie &#39;@id = @O5iRp40EGA&#39; niet parseren. | 404 - Kan PKey niet decoderen. (PKey=@jksad) |
| Een ongeldige PKey gebruiken in URI | 500 - het attribuut &quot;O5iRp40EGA&quot;onbekend (zie definitie van &quot;Profielen (nms :recipient)&quot;schema). XTK-170036 Kan expressie &#39;@id = @O5iRp40EGA&#39; niet parseren. | 404 - Kan PKey niet decoderen. (PKey=@jksad) Niet-ondersteund eindpunt. (eindpunt=rest/profielAndServices/profiel/@jksad) |
| Twee verschillende onbewerkte sleutels in URI gebruiken en verzoek lichaam | 500 - RST-360011 Er is een fout opgetreden. Neem contact op met de beheerder. RST-360012 Inconsistente verrichting op middel &quot;dienst&quot; - kan sleutel &quot;SVC3&quot;aan &quot;SVC4&quot;niet bijwerken. | 500 - Er is een fout opgetreden. Neem contact op met de beheerder. |
| PKey gebruiken in URI en een verschillende ruwe PKey in het verzoeklichaam | 500 - Er bestaat al een &#39;service&#39; met dezelfde sleutel &#39;SVC4&#39;. PGS-220000 PostgreSQL-fout: FOUT: dubbele sleutelwaarde schendt unieke beperking &quot;nmsservice_name&quot; DETAIL: Sleutel (naam)=(SVC4) bestaat al. | 500 - Er is een fout opgetreden. Neem contact op met de beheerder. |
| Niet-bestaande raw-id gebruiken in URI | 404 - RST-360011 Er is een fout opgetreden. Neem contact op met de beheerder. Kan document met pad &#39;Service&#39; van sleutel &#39;adobe_nl :0&#39; (document met schema&#39;service&#39; en naam &#39;adobe_nl&#39;) niet vinden. | 404 - Kan document met pad &#39;Service&#39; van sleutel &#39;adobe_nl&#39; niet vinden (document met schema&#39;service&#39; en naam &#39;adobe_nl&#39;) |
| Niet-bestaande raw-id gebruiken in aanvraagbody | 404 - RST-360011 Er is een fout opgetreden. Neem contact op met de beheerder. Document met pad &#39;Service&#39; van sleutel &#39;adobe_nl&#39; kan niet worden gevonden (document met schema&#39;service&#39; en naam &#39;adobe_nl&#39;) | 404 - Kan document met pad &#39;Service&#39; van sleutel &#39;adobe_nl&#39; niet vinden (document met schema&#39;service&#39; en naam &#39;adobe_nl&#39;) |
| - | 500 - RST-360011 Er is een fout opgetreden. Neem contact op met de beheerder. | 500 - Er is een fout opgetreden. Neem contact op met de beheerder. |
| Een profiel/service met een ongeldige waarde voor het geslacht (of iets anders) invoegen | 500 - RST-360011 Er is een fout opgetreden. Neem contact op met de beheerder. De waarde &quot;ongeldig&quot;is ongeldig voor de &quot;nms :recipient: gender&quot;opsomming van het &quot;@gender&quot;gebied | 500 -Er is een fout opgetreden. Neem contact op met de beheerder. |

## Profiel - tijdzone

Met Campaign Standard, wordt timezone getoond als deel van de reactie JSON van **profileAndServices/profile** REST API vraag.

Met Campagne v8, wordt timezone slechts getoond aan gebruiker als deel van **profileAndServicesExt/profile** REST API vraag. Het maakt geen deel uit van **profileAndServices/profile** REST API vraag aangezien het in een uitgebreid schema wordt toegevoegd.

## Workflows - externe signaalactivering

Campaign Standard Workflow GET API retourneert parameternamen zoals de werkstroominstantievariabelen en hun gegevenstypen (boolean, string, etc.). Dit wordt gebruikt om correct geformatteerde JSON- verzoeklichaam tot stand te brengen wanneer het teweegbrengen van het signaal via een POST API vraag.

Campaign v8 biedt geen ondersteuning voor instantievariabelen van advertentieworkflows, maar verwacht dat ontwikkelaars weten wat dat zijn. Daarom moet na de migratie parameterinformatie in de instantie van de POST-aanvraag worden samengesteld zonder de beschikbaarheid van parameterinformatie in de GET API-respons.

<!--## Transactional messages

* With Campaign Standard, a POST request returns empty fields for elements and attributes in the request body. With Campaign v8, the response returns values that match the ones in the request body instead.

* When publishing an event configuration, the API preview panel displays the REST URL alongside the request body syntax.

    Since Campaign v8 does not support event configuration fields definition (event creation is just adding a value to eventType enumeration), there is no API preview panel when adding an event type. The REST URL is displayed  in the transactional message user interface once an event transactional message is published.-->
