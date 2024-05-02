---
title: Lijst met componenten
description: Hier vindt u de lijst met alle componenten die beschikbaar zijn in dynamische rapporten en de bijbehorende definities.
level: Beginner
audience: end-user
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: b11d696767209145511b38735f22275a38676ade
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 1%

---

# Lijst met componenten {#list-of-components}

Als twee componenten niet compatibel zijn, wordt de waarde in de cel weergegeven. **Geen**.

## Dimensies {#dimensions}

In de onderstaande tabel vindt u een overzicht van de afmetingen die in rapporten en de definities daarvan worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br/> </th> 
   <th> Definitie<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Browser<br/> </td> 
   <td> Browser waarvan het bericht werd geopend of aangeklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Campagne<br/> </td> 
   <td> Label en id van uw campagne.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aflevering<br/> </td> 
   <td> Label en id van de levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Apparaat<br/> </td> 
   <td> Apparaat van waaruit de e-mail/SMS/push-melding is geopend/bekeken/aangeklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Mislukt<br/> </td> 
   <td> Typen fouten die stuitingen veroorzaakten voor elke levering, bijvoorbeeld onbekend gebruiker, ongeldig domein of postbus vol.<br/> </td> 
  </tr> 
  <tr> 
   <td> Naam van mobiele toepassing<br/> </td> 
   <td> Naam van de mobiele toepassing<br/> </td> 
  </tr>
  <tr> 
   <td> Platform<br/> </td> 
   <td> Platform van het apparaat waarvan het bericht werd geopend/bekeken/aangeklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Profiel<br/> </td> 
   <td> Hiermee groepeert u de velden voor het out-of-the-box- en aangepaste profiel die tijdens de uitbreiding van de profielbron zijn gemaakt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Ontvangerdomein<br/> </td> 
   <td> Domein dat wordt gebruikt om de e-mail te openen.<br/> </td> 
  </tr> 
  <tr> 
   <td> Terugkerende levering<br/> </td> 
   <td> Label en id van de terugkerende levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Domein afzender<br/> </td> 
   <td> Domein dat wordt gebruikt om de e-mail te verzenden.<br/> </td> 
  </tr> 
  <tr> 
   <td> IP van afzender<br/> </td> 
   <td> IP gebruikt om e-mail te verzenden.<br/> </td> 
  </tr> 
  <tr> 
   <td> URL bijhouden<br/> </td> 
   <td> URL waarop de gebruiker via het bericht heeft geklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Categorie URL bijhouden<br/> </td> 
   <td> Categorie die is toegewezen aan de URL voor bijhouden.<br/> </td> 
  </tr> 
  <tr> 
   <td> URL-label bijhouden<br/> </td> 
   <td> Label dat aan de URL wordt gegeven, zoals de spiegel, neemt contact met ons op of opent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Transactionele levering<br/> </td> 
   <td> Label en id van de levering voor de transactie.<br/> </td> 
  </tr> 
  <tr> 
   <td> Variant<br/> </td> 
   <td> Variant van het e-mailbericht in het geval van A/B-tests.<br/> </td> 
  </tr> 
 </tbody> 
</table>

## Metrics {#metrics}

De lijsten hieronder geven u de lijst van metriek die in rapporten en hun definities afhankelijk van het leveringstype wordt gebruikt.

### E-mailmeetgegevens {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrisch<br/> </th> 
   <th> Definitie<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Op lijst van gewezen personen<br/> </td> 
   <td> Aantal ontvangers die een e-mailbericht hebben gedeclareerd als spam of junk.<br/> </td> 
  </tr> 
  <tr> 
   <td> Lijst van gewezen personen<br/> </td> 
   <td> Percentage van de op de lijst van gewezen personen aangegeven leveringen.<br/> </td> 
  </tr> 
  <tr> 
   <td> Bounces + fouten<br/> </td> 
   <td> Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie<br/> </td> 
   <td> Percentage van e-mailberichten dat is teruggestuurd in vergelijking met verzonden e-mail.<br/> </td> 
  </tr> 
  <tr> 
   <td> Klikken<br/> </td> 
   <td> Het aantal keren dat op een inhoud is geklikt in een levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Klikken tot snelheid<br/> </td> 
   <td> Percentage van klikken in een levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br/> </td> 
   <td> Het aantal berichten dat is verzonden in verhouding tot het totale aantal verzonden berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde rente<br/> </td> 
   <td> Percentage berichten verzonden.<br/> </td> 
  </tr> 
  <tr> 
   <td> Hard stuiteren<br/> </td> 
   <td> Het totale aantal permanente fouten, zoals een onjuist e-mailadres.<br/> </td> 
  </tr> 
  <tr> 
   <td> Harde stuitsnelheid<br/> </td> 
   <td> Percentage leveringen dat is mislukt door permanente fouten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen<br/> </td> 
   <td> Aantal ontvangers die op de verbinding van de spiegelpagina klikte.<br/> </td> 
  </tr> 
  <tr> 
   <td> Paginasnelheid spiegelen<br/> </td> 
   <td> Percentage van klikken op de verbinding van de spiegelpagina vergeleken met de totale leveringsberichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingen klikken<br/> </td> 
   <td> Aantal tijd waarop op een voorstel is geklikt in een levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aanbiedingskliktarief<br/> </td> 
   <td> Percentage van klikken op een aanbieding.<br/> </td> 
  </tr> 
  <tr> 
   <td> Openen<br/> </td> 
   <td> Aantal keren dat een bericht in een levering werd geopend.<br/> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br/> </td> 
   <td> Percentage geopende berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br/> </td> 
   <td> Het totale aantal verzendt voor de levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br/> </td> 
   <td> Aantal berichten die in quarantaine van het adres stuitten en resulteerden.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarantaine<br/> </td> 
   <td> Percentage quarantines vergeleken met verzonden berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Geweigerd<br/> </td> 
   <td> Aantal berichten die als spam door de servers SMTP worden geclassificeerd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Geweigerde snelheid<br/> </td> 
   <td> Percentage berichten gemarkeerd als afgewezen.<br/> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuit<br/> </td> 
   <td> Het totale aantal tijdelijke fouten, zoals een volledig postvak.<br/> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuitsnelheid<br/> </td> 
   <td> Percentage leveringen dat om tijdelijke redenen is mislukt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br/> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering hebben geklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unieke openingen<br/> </td> 
   <td> Aantal ontvangers dat de levering heeft geopend.<br/> </td> 
  </tr> 
  <tr> 
   <td> Uniek geabonneerd<br/> </td> 
   <td> Aantal ontvangers die op de unsubscription-koppeling hebben geklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br/> </td> 
   <td> Aantal unieke uitschrijving in vergelijking met de geleverde berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opgezegd<br/> </td> 
   <td> Aantal klikken op de verbinding van het unsubscription.<br/> </td> 
  </tr> 
 </tbody> 
</table>

<!--
### Push notification metrics {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bounces + Errors<br/> </td> 
   <td> Total of errors cumulated during delivery in relation to the total number of sent messages, e.g. errors from MCPNS or provider.<br/> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br/> </td> 
   <td> Percentage of push notifications that bounced compared to push notifications sent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Click<br/> </td> 
   <td> Number of times a push notification has been delivered to the device and clicked on by the user. The user either wanted to view the notification, which will then be moved to Push Open tracking, or dismiss it.<br/> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br/> </td> 
   <td> Percentage of users who interacted with the push notification.<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> Number of push notifications successfully sent, in relation to the total number of sent push notifications.<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br/> </td> 
   <td> Percentage of push notifications successfully sent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> Number of times a push notification has been delivered to the device and left untouched in the notification center. In most cases, impressions number should be similar to the delivered number. This ensures that the device got the message and relayed that information back to the server.<br/> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> Total number of push notifications sent.<br/> </td> 
  </tr> 
  <tr> 
   <td> Open<br/> </td> 
   <td> Total number of push notifications delivered to the device and clicked on by users thus opening the app. This is similar to the Push Click except a Push Open will not be triggered if the notification was dismissed.<br/> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br/> </td> 
   <td> Percentage of opened push notifications.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique clicks<br/> </td> 
   <td> Number of times a unique user interacts with the push notification, e.g. clicks on the notification or button.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> Number of impressions by recipient.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique Opens<br/> </td> 
   <td> Number of recipients who opened the delivery.<br/> </td> 
  </tr> 
 </tbody> 
</table>

### In-App metrics {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metric<br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> Total number of In-App messages delivered to the device by the service provider.<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> Total of In-App messages seen by recipients depending on whether trigger criterion was met.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App clicks <br/> </td> 
   <td> Total number of recipients who clicked on Button 1 or Button 2.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App click through rate<br/> </td> 
   <td> Percentage of users who clicked on Button 1 or Button 2 compared to users who saw the message.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal<br/> </td> 
   <td> Total number of messages that recipients dismissed either by clicking the close button or auto-dismiss.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal rate<br/> </td> 
   <td> Percentage of In-App messages that recipients dismissed.<br/> </td> 
  </tr> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> Total number of In-App messages sent from Adobe Campaign as part of the delivery sent process.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> Number of impressions by a unique recipient.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App clicks<br/> </td> 
   <td> Number of times recipients clicked on Button 1 or Button 2.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App dismissals<br/> </td> 
   <td> Number of time recipients dismissed an In-App message.<br/> </td> 
  </tr> 
 </tbody> 
</table>
-->

## Segmenten {#segments}

In de onderstaande tabel vindt u een lijst met segmenten die in rapporten en de bijbehorende definities worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Segment<br/> </th> 
   <th> Definitie<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Leeftijd: Boomers 1<br/> </td> 
   <td> Ontvangers geboren van 1946 tot 1954.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Boomers 2<br/> </td> 
   <td> Ontvangers geboren van 1955 tot 1965.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 18 tot 25 jaar<br/> </td> 
   <td> Ontvangers van 18 tot 25 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 26 tot 30 jaar<br/> </td> 
   <td> Ontvangers van 26 tot 30 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 31 tot 40<br/> </td> 
   <td> Ontvangers van 31 tot 40 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 41 tot 50<br/> </td> 
   <td> Ontvangers van 41 tot 50 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: generatie X<br/> </td> 
   <td> Ontvangers geboren van 1966 tot 1976.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: generatie Y (miljoenen)<br/> </td> 
   <td> Ontvangers, geboren van 1977 tot 1994.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: generatie Z<br/> </td> 
   <td> Ontvangers geboren van 1995 tot vandaag.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: groter dan 50<br/> </td> 
   <td> Ontvangers die ouder zijn dan 50 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: minder dan 25 jaar<br/> </td> 
   <td> Ontvangers die jonger zijn dan 25 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> leeftijd: minder dan 30<br/> </td> 
   <td> Ontvangers die jonger zijn dan 30 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> leeftijd: minder dan 40<br/> </td> 
   <td> Ontvangers die jonger zijn dan 40 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: minder dan 50<br/> </td> 
   <td> Ontvangers die jonger zijn dan 50 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: stille generatie<br/> </td> 
   <td> Ontvangers geboren in 1945 of eerder.<br/> </td> 
  </tr> 
  <tr> 
   <td> Alle bezoeken<br/> </td> 
   <td> Elke ontvanger<br/> </td> 
  </tr>
 </tbody> 
</table>
