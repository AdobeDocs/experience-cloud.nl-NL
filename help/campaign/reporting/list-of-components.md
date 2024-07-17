---
title: Lijst met componenten
description: Hier vindt u de lijst met alle beschikbare componenten in     Dynamische rapporten en hun definities.
level: Beginner
audience: end-user
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 5c58db92-7878-4c70-b076-a393f1cda8b7
source-git-commit: 34c6f8a137a9085b26c0ea8f78930cff6192cfc9
workflow-type: tm+mt
source-wordcount: '770'
ht-degree: 0%

---

# Lijst met componenten {#list-of-components}

Merk op dat als twee componenten niet compatibel zijn, de cel de waarde **niets** zal tonen.

## Dimensionen {#dimensions}

In de onderstaande tabel vindt u een overzicht van de afmetingen die in rapporten en de definities daarvan worden gebruikt.

<table> 
 <thead> 
  <tr> 
   <th> Dimension <br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Browser <br/> </td> 
   <td> Browser waarvan het bericht werd geopend of aangeklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Campagne <br/> </td> 
   <td> Etiket en identiteitskaart van uw campagne.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aflevering <br/> </td> 
   <td> Etiket en identiteitskaart van de levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Apparaat <br/> </td> 
   <td> Apparaat van waaruit de e-mail/SMS/push-melding werd geopend/bekeken/aangeklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Redenen voor fout <br/> </td> 
   <td> Typen fouten die stuitingen voor elke levering hebben veroorzaakt, bijvoorbeeld onbekende gebruiker, ongeldig domein of postbus vol.<br/> </td> 
  </tr> 
  <tr> 
   <td> Naam van mobiele toepassing <br/> </td> 
   <td> Naam van de mobiele toepassing <br/> </td> 
  </tr>
  <tr> 
   <td> Platform <br/> </td> 
   <td> Platform van het apparaat waarvan het bericht werd geopend/bekeken/kliked.<br/> </td> 
  </tr> 
  <tr> 
   <td> Profiel <br/> </td> 
   <td> Reggroepeert uit-van-de-doos en de gebieden van het douaneprofiel die tijdens de uitbreiding van het profielmiddel worden gecreeerd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Ontvangerdomein <br/> </td> 
   <td> Domein dat wordt gebruikt om e-mail te openen.<br/> </td> 
  </tr> 
  <tr> 
   <td> Terugkerende levering <br/> </td> 
   <td> Etiket en identiteitskaart van de terugkomende levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Het domein van de afzender <br/> </td> 
   <td> Domein dat wordt gebruikt om e-mail te verzenden.<br/> </td> 
  </tr> 
  <tr> 
   <td> IP van afzender <br/> </td> 
   <td> IP gebruikte om e-mail te verzenden.<br/> </td> 
  </tr> 
  <tr> 
   <td> URL bijhouden <br/> </td> 
   <td> URL die door de gebruiker van het bericht werd aangeklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Categorie URL bijhouden <br/> </td> 
   <td> Categorie die aan volgende URL wordt toegewezen.<br/> </td> 
  </tr> 
  <tr> 
   <td> URL-label bijhouden <br/> </td> 
   <td> Label dat aan de URL wordt gegeven, zoals spiegel, contacteer ons of open.<br/> </td> 
  </tr> 
  <tr> 
   <td> Transactionele levering <br/> </td> 
   <td> Etiket en identiteitskaart van de transactionele levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Variant <br/> </td> 
   <td> Variant van de e-mail in het geval van A/B-tests.<br/> </td> 
  </tr> 
 </tbody> 
</table>

## Metrics {#metrics}

De lijsten hieronder geven u de lijst van metriek die in rapporten en hun definities afhankelijk van het leveringstype wordt gebruikt.

### E-mailmeetgegevens {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrisch <br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Op lijst van gewezen personen <br/> </td> 
   <td> Aantal ontvangers die een e-mail als spam of junk hebben verklaard.<br/> </td> 
  </tr> 
  <tr> 
   <td> Lijst van gewezen personen rate <br/> </td> 
   <td> Percentage leveringen gemarkeerd op lijst van gewezen personen.<br/> </td> 
  </tr> 
  <tr> 
   <td> Stuiterwaarden + fouten <br/> </td> 
   <td> Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie <br/> </td> 
   <td> Percentage verzonden e-mailberichten dat is teruggestuurd in vergelijking met verzonden e-mail.<br/> </td> 
  </tr> 
  <tr> 
   <td> Klikken <br/> </td> 
   <td> Aantal tijden een inhoud in een levering werd geklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Klikken door snelheid <br/> </td> 
   <td> Percentage van kliks in een levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Geleverd <br/> </td> 
   <td> Aantal met succes verzonden berichten, met betrekking tot het totale aantal verzonden berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde snelheid <br/> </td> 
   <td> Percentage van met succes verzonden berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Hard stuiteren <br/> </td> 
   <td> Het totale aantal permanente fouten, zoals een verkeerd e-mailadres.<br/> </td> 
  </tr> 
  <tr> 
   <td> Harde stuitsnelheid <br/> </td> 
   <td> Percentage leveringen dat is mislukt als gevolg van permanente fouten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen <br/> </td> 
   <td> Aantal ontvangers die op de verbinding van de spiegelpagina klikte.<br/> </td> 
  </tr> 
  <tr> 
   <td> Paginasnelheid spiegelen <br/> </td> 
   <td> Percentage van klikken op de verbinding van de spiegelpagina vergeleken met de totale leveringsberichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aanbieding klikt <br/> </td> 
   <td> Aantal tijd een aanbieding in een levering werd geklikt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Aanbieding met klikfrequentie <br/> </td> 
   <td> Percentage van klikken op een aanbieding.<br/> </td> 
  </tr> 
  <tr> 
   <td> Openen <br/> </td> 
   <td> Aantal tijden een bericht in een levering werd geopend.<br/> </td> 
  </tr> 
  <tr> 
   <td> Open rate <br/> </td> 
   <td> Percentage van geopende berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden <br/> </td> 
   <td> Het totale aantal verzendt voor de levering.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarantine <br/> </td> 
   <td> Aantal berichten die in quarantaine van het adres stuitten en resulteerden.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarantainerfrequentie <br/> </td> 
   <td> Percentage quarantines vergeleken met verzonden berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Afgewezen <br/> </td> 
   <td> Aantal berichten die als spam door de servers SMTP worden geclassificeerd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Geweigerde snelheid <br/> </td> 
   <td> Percentage van berichten duidelijk zoals verworpen.<br/> </td> 
  </tr> 
  <tr> 
   <td> Zacht stuiteren <br/> </td> 
   <td> Het totale aantal tijdelijke fouten, zoals volledig inbox.<br/> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuitsnelheid <br/> </td> 
   <td> Percentage leveringen dat vanwege een tijdelijke reden is mislukt.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken <br/> </td> 
   <td> Aantal ontvangers die op een inhoud in een levering klikte.<br/> </td> 
  </tr> 
  <tr> 
   <td> Uniek wordt geopend <br/> </td> 
   <td> Aantal ontvangers die de levering opende.<br/> </td> 
  </tr> 
  <tr> 
   <td> Uniek niet-geabonneerd <br/> </td> 
   <td> Aantal ontvangers die op de unsubscription verbinding klikte.<br/> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen <br/> </td> 
   <td> Aantal unieke unsubscription in vergelijking met de geleverde berichten.<br/> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribed <br/> </td> 
   <td> Aantal klikken op de unsubscription verbinding.<br/> </td> 
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
   <th> Segment <br/> </th> 
   <th> Definition<br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Leeftijd: Boomers 1 <br/> </td> 
   <td> Ontvangers geboren van 1946 tot 1954.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Boomers 2 <br/> </td> 
   <td> Ontvangers geboren van 1955 tot 1965.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: 18 tot 25 jaar <br/> </td> 
   <td> Ontvangers van 18 tot 25 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 26 tot 30 <br/> </td> 
   <td> Ontvangers van 26 tot 30 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 31 tot 40 <br/> </td> 
   <td> Ontvangers van 31 tot 40 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: van 41 tot 50 <br/> </td> 
   <td> Ontvangers van 41 tot 50 jaar oud.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie X <br/> </td> 
   <td> Ontvangers geboren van 1966 tot 1976.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie Y (Miljarigen) <br/> </td> 
   <td> Ontvangers geboren van 1977 tot 1994.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: Generatie Z<br/> </td> 
   <td> Ontvangers geboren van 1995 tot vandaag.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: groter dan 50 <br/> </td> 
   <td> Ontvangers die ouder zijn dan 50 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: minder dan 25 <br/> </td> 
   <td> Ontvangers die jonger zijn dan 25 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: minder dan 30 <br/> </td> 
   <td> Ontvangers die jonger zijn dan 30 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: minder dan 40 <br/> </td> 
   <td> Ontvangers die jonger zijn dan 40 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: minder dan 50 <br/> </td> 
   <td> Ontvangers die jonger zijn dan 50 jaar.<br/> </td> 
  </tr> 
  <tr> 
   <td> Leeftijd: stille generatie <br/> </td> 
   <td> Ontvangers geboren in 1945 of eerder.<br/> </td> 
  </tr> 
  <tr> 
   <td> Alle bezoeken <br/> </td> 
   <td> Elke ontvanger <br/> </td> 
  </tr>
 </tbody> 
</table>
