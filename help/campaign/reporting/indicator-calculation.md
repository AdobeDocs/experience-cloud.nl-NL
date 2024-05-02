---
title: Indicatoren berekenen
description: Begrijp de resultaten van uw rapporten met een lijst van elke metrische formule.
level: Intermediate
audience: end-user
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 031d5b692d9b9e4420b14ba1ab892fbafed57ec0
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---

# Indicatoren berekenen{#indicator-calculation}

>[!NOTE]
>
>Om hoge volumes en real-time analyses beter te verwerken en te beheren, gebruikt de dynamische rapportering benaderende aggregaties voor verschillende telramingen. De geschatte samenvoegingen bieden een beperkt geheugengebruik en zijn vaak sneller dan nauwkeurige berekeningen.

De onderstaande tabellen bevatten een lijst met indicatoren die in de verschillende verslagen worden gebruikt en de berekeningsformule, afhankelijk van het leveringstype.

## E-maillevering {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br/> </th> 
   <th> <strong>Veldnaam</strong> <br/> </th> 
   <th> <strong>Indicatorberekeningsformule</strong> <br/> </th> 
   <th> <strong>Opmerkingen</strong><br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Account uitgeschakeld<br/> </td> 
   <td> @disabled<br/> </td> 
   <td> count(@failureReason=4)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Op lijst van gewezen personen<br/> </td> 
   <td> @blacklist<br/> </td> 
   <td> count(@failureReason=8, @failureType=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Lijst van gewezen personen<br/> </td> 
   <td> @rateBlacklist<br/> </td> 
   <td> @blacklist/@sent<br/> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br/> </td> 
  </tr> 
  <tr> 
   <td> Bounces + fouten<br/> </td> 
   <td> @bounces<br/> </td> 
   <td> count(@status=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie<br/> </td> 
   <td> @rateBounces<br/> </td> 
   <td> @bounces/@sent<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Klikken<br/> </td> 
   <td> @clicks<br/> </td> 
   <td> count(@trackingUrlType=1, 10 of 11)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Klikken tot snelheid<br/> </td> 
   <td> @clickthrough<br/> </td> 
   <td> @uniqueclicks/@bezorgd<br/> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br/> </td> 
   <td> @loaded<br/> </td> 
   <td> count(@status=1)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde rente<br/> </td> 
   <td> @rateDelivered<br/> </td> 
   <td> @delivery/@sent<br/> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br/> </td> 
  </tr> 
  <tr> 
   <td> Harde vlekken<br/> </td> 
   <td> @hardBounces<br/> </td> 
   <td> count(@failureType=2 EN @failureReason=8)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fel-stallatiesnelheid<br/> </td> 
   <td> @rateHardBounces<br/> </td> 
   <td> @hardBounces/@sent<br/> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br/> </td> 
  </tr> 
  <tr> 
   <td> Ongeldig domein<br/> </td> 
   <td> @invalidDomain<br/> </td> 
   <td> count(@failureReason=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Postbus vol<br/> </td> 
   <td> @mailBoxFull<br/> </td> 
   <td> count(@failureReason=5)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen<br/> </td> 
   <td> @mirrorPage<br/> </td> 
   <td> count(@trackingUrlType=6)<br/> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Paginasnelheid spiegelen<br/> </td> 
   <td> @rateMirrorPage<br/> </td> 
   <td> @mirrorPage/@loaded<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Niet verbonden<br/> </td> 
   <td> @notConnected<br/> </td> 
   <td> count(@failureReason=6)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Openen<br/> </td> 
   <td> @uniqueOpens<br/> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br/> </td> 
   <td> @rateOpens<br/> </td> 
   <td> @Opens/@bezorgd<br/> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br/> </td> 
   <td> @quarantaine<br/> </td> 
   <td> isQuarantine=true<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Quarantaine<br/> </td> 
   <td> @rateQuarantine<br/> </td> 
   <td> @quarantaine/@verzonden<br/> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br/> </td> 
  </tr>
  <tr> 
   <td> Geweigerd<br/> </td> 
   <td> @geweigerd<br/> </td> 
   <td> count(@failureReason=20, @failureType=2)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Geweigerde snelheid<br/> </td> 
   <td> @rateRejected<br/> </td> 
   <td> @geweigerd/@verzonden<br/> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br/> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br/> </td> 
   <td> @sent<br/> </td> 
   <td> @delivery + @bounces<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuit<br/> </td> 
   <td> @softBounces<br/> </td> 
   <td> count(@failureType=1)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuitsnelheid<br/> </td> 
   <td> @rateSoftBounces<br/> </td> 
   <td> @softBounces/@sent<br/> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br/> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br/> </td> 
   <td> @uniqueclicks<br/> </td> 
   <td> De unieke kliks wordt berekend gebruikend de concepten van de Schets. </a>.<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke openingen<br/> </td> 
   <td> @uniqueOpenen<br/> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Onbereikbaar <br/> </td> 
   <td> @onbereikbaar<br/> </td> 
   <td> count(@failureReason=3)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br/> </td> 
   <td> @unsubscribes<br/> </td> 
   <td> count(@trackingUrlType=3)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br/> </td> 
   <td> @rateUnsubscribes<br/> </td> 
   <td> @unsubscribes/@loaded<br/> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br/> </td> 
  </tr> 
  <tr> 
   <td> Gebruiker onbekend<br/> </td> 
   <td> @unknownUser<br/> </td> 
   <td> count(@failureReason=1)<br/> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

<!--
## Push notification delivery {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br/> </th> 
   <th> <strong>Field name</strong> <br/> </th> 
   <th> <strong>Indicator calculation formula</strong> <br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> @sent<br/> </td> 
   <td> @count(status=sent)<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> @delivered<br/> </td> 
   <td> @count(status=delivered)<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered rate<br/> </td> 
   <td> @rateDelivered<br/> </td> 
   <td> (@delivered/@sent)*100<br/> </td> 
  </tr> 
  <tr> 
   <td> Bounce + Error rate<br/> </td> 
   <td> @rateBounces<br/> </td> 
   <td> (@delivered/@sent)*100<br/> </td> 
  </tr> 
  <tr> 
   <td> Open<br/> </td> 
   <td> @opens<br/> </td> 
   <td> @count(status=open)<br/> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br/> </td> 
   <td> @rateOpens<br/> </td> 
   <td> (@opens/@delivered)*100<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique opens<br/> </td> 
   <td> @uniqueopens<br/> </td> 
   <td> Unique opens is calculated using ThetaSketch concepts of unique RecipientIds.<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> @impressions<br/> </td> 
   <td> @count(status=delivered)<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> @uniqueimpressions<br/> </td> 
   <td> @unique(@count(status=view))<br/> </td> 
  </tr> 
  <tr> 
   <td> Click<br/> </td> 
   <td> @clicks<br/> </td> 
   <td> @count(status=interact)<br/> </td> 
  </tr> 
  <tr> 
   <td> Unique clicks<br/> </td> 
   <td> @uniqueclicks<br/> </td> 
   <td> Unique clicks is calculated using ThetaSketch concepts.<br/> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br/> </td> 
   <td> @clickthrough<br/> </td> 
   <td> (@interact/@delivered)*100<br/> </td> 
  </tr> 
 </tbody> 
</table>

## In-App delivery {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br/> </th> 
   <th> <strong>Field name</strong> <br/> </th> 
   <th> <strong>Indicator calculation formula</strong> <br/> </th> 
   <th> <strong>Comments</strong><br/> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processed/sent<br/> </td> 
   <td> @sent<br/> </td> 
   <td> @count(status=sent)<br/> </td> 
   <td> sent=delivered<br/> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br/> </td> 
   <td> @delivered<br/> </td> 
   <td> @count(status=delivered)<br/> </td> 
   <td> delivered=sent<br/> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br/> </td> 
   <td> @impressions<br/> </td> 
   <td> @count(status=view) or @count(status=button 1 click + button 2 click + dismissals)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique impressions<br/> </td> 
   <td> @uniqueimpressions<br/> </td> 
   <td> @unique(@count(status=view))<br/> </td> 
   <td> For <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> template, user = Recipient Id.<br/> For <span class="uicontrol">Target all users of a Mobile app (inAppBroadcast)</span> and <span class="uicontrol">Target users based on their Mobile profile (inApp)</span> templates, user = MC Id or equivalent that represents a unique combination of user, mobile app and device.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App clicks <br/> </td> 
   <td> @inappclicks<br/> </td> 
   <td> @count (status=click)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App clicks<br/> </td> 
   <td> @uniqueinapp<br/> </td> 
   <td> @unique(@count (status=clicks))<br/> </td> 
   <td> For <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> template, user = Recipient Id.<br/> For <span class="uicontrol">Target all users of a Mobile app (inAppBroadcast)</span> and <span class="uicontrol">Target users based on their Mobile profile (inApp)</span> templates, user = MC Id or equivalent that represents a unique combination of user, mobile app and device.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App click through rate<br/> </td> 
   <td> @inappclickthrough<br/> </td> 
   <td> Total clicks on Button 1 or Button 2/total impressions*100<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal<br/> </td> 
   <td> @dismissal<br/> </td> 
   <td> @count (status=close)<br/> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unique In-App dismissals<br/> </td> 
   <td> @uniquedismissal<br/> </td> 
   <td> @unique(@count (status=close))<br/> </td> 
   <td> For <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> template, user = Recipient Id.<br/> For <span class="uicontrol">Target all users of a Mobile app (inAppBroadcast)</span> and <span class="uicontrol">Target users based on their Mobile profile (inApp)</span> templates, user = MC Id or equivalent that represents a unique combination of user, mobile app and device.<br/> </td> 
  </tr> 
  <tr> 
   <td> In-App dismissal rate<br/> </td> 
   <td> @dismissalrate<br/> </td> 
   <td> Total close/total impressions*100<br/> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
-->