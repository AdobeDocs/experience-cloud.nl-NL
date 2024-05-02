---
title: Branding
description: Ontdek alle tools die beschikbaar zijn om uw brandingsidentiteiten te beheren
audience: administration
context-tags: branding,overview;branding,main
role: Admin
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 51abadc86b97097d13824651d8c50d4ddd014a51
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 16%

---

# Aan de slag met branding {#branding-gs}

>[!IMPORTANT]
>
>Merken kunnen niet door eindgebruikers worden gemaakt of gewijzigd. Deze bewerkingen moeten worden uitgevoerd door de technische beheerder van Adobe Campaign. Neem voor elk verzoek contact op met de klantenservice van Adobe.

Elk bedrijf heeft merkrichtlijnen die zowel visuele elementen als technische details bepalen. Adobe Campaign helpt u deze richtlijnen centraal te beheren, zodat u een consistent merkimago aan uw klanten kunt presenteren in alles wat u doet, van logo&#39;s in e-mails tot de URL&#39;s en domeinen die in uw campagnes worden gebruikt.

Technische beheerders kunnen meerdere merken binnen Adobe Campaign maken en beheren. Op deze manier kunt u alle elementen definiëren waaruit uw merkidentiteit bestaat, inclusief logo&#39;s en zelfs instellingen voor het bijhouden van e-mail. Nadat u deze merken hebt gemaakt, kunt u ze gemakkelijk koppelen aan uw leveringen.

U kunt nieuwe entiteiten van uw organisatie toevoegen in Campagne, of een nieuw type van e-mail tot stand brengen dat u onder een verschillend subdomain moet verzenden. Volg onderstaande stappen om dit te doen:

1. **Een nieuw subdomein configureren** - Voor om het even welk nieuw subdomain dat door Adobe moet worden gebruikt, zal de eerste stap het vormen zijn. U kunt dit via [Campagne](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=nl) of neem contact op met uw technische Adobe. Meer informatie over subdomeinconfiguratie [op deze pagina](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-domain-name-setup).

   >[!NOTE]
   >
   >Het configuratiescherm is toegankelijk voor alle gebruikers met beheerdersrechten. De stappen om toegang met beheerdersrechten aan een gebruiker te verlenen worden gedetailleerd beschreven op [deze pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=nl#discover-control-panel).

1. **Een leveringssjabloon maken** - Zodra het nieuwe merk beschikbaar is, is het de beste manier om ten minste één nieuwe lege leveringstemplate te maken die naar dit nieuwe merk verwijzen. [Meer informatie](branding-assign.md).

1. **Richtlijnen voor levering controleren** - Voordat u begint met het gebruik van het nieuwe domein, moet de strategie worden besproken met het team voor aflevering van Adobe. Zij zullen helpen om de beste praktijken te bepalen, als een nieuwe affiniteit zou moeten worden gecreeerd om IPs tussen domeinen bijvoorbeeld te verdelen, en/of als een platforminplan zou moeten worden bepaald.

