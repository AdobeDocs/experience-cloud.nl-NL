---
title: Adobe Campaign Web User Interface
description: 64-bits tabellen
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# 64-bits schema&#39;s {#sixty-four-bit-tables}

Om de overgang van Campaign Standard naar Campaign v8 te vergemakkelijken, zijn verschillende tabellen gewijzigd van 32 naar 64 bits. Campaign Standard ondersteunt 64-bits PK in verschillende out-of-the-box schema&#39;s, terwijl Campagne v8 32-bits PK in de meeste schema&#39;s ondersteunt.

## Beperkingen

* Deze technische wijziging geldt alleen voor klanten die vanuit Campaign Standard migreren.
* Het schema en de uitzendingsuitbreiding worden niet gesteund in 64 beetjes. Het zal in 32 beetjes blijven.
* Logbestanden die betrekking hebben op leveringen die naar technische gebruikers worden verzonden, zijn niet beschikbaar in Campagne v8.
* Alleen PostSQL wordt ondersteund.

## Gewijzigde schema&#39;s

Hier is de lijst van schema&#39;s veranderd in 64 beetjes en hun gewijzigde attributen.

| Schemanaam | Naam van kenmerk |
|--- |--- |
| nms:broadLogRcp | id |
| nms:trackingLogRcp | id |
| nms:excludeLogRcp | id |
| nms:broadLogVisitor | id |
| nms:trackingLogVisitor | id |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | id |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | id |
| nms:trackingLogAppSubRcp | id |
| nms:excludeLogAppSubRcp | id |
| nms:webEvent | wideLogSrc-id, wideLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
