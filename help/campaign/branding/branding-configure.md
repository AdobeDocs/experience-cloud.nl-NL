---
title: Branding
description: Ontdek hoe u uw merk kunt configureren
audience: administration
context-tags: branding,overview;branding,main
role: Admin
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
exl-id: 7afc802d-e90c-48c8-aa04-3ea543dfdfbc
source-git-commit: 62c2f2e7a6f5dd347749e963a655b717cd5c7310
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 26%

---

# Brandmerken configureren {#branding-configure}

>[!IMPORTANT]
>
>Merken kunnen niet door eindgebruikers worden gemaakt of gewijzigd. Deze bewerkingen moeten worden uitgevoerd door de technische beheerder van Adobe Campaign. Neem voor elk verzoek contact op met de klantenservice van Adobe.

In Adobe Campaign V8 staan de merken in het menu **[!UICONTROL Administration > Platform > Branding]** .

A **[!UICONTROL Brand]** wordt bepaald door de volgende kenmerken:

* An **[!UICONTROL Identity]**, which define and personalizes your brand. Deze sectie bevat de volgende velden:

   * **[!UICONTROL Label]** zichtbaar in de interface
   * **[!UICONTROL ID]**
   * **[!UICONTROL Brand name]**
   * **[!UICONTROL Website URL]** en **[!UICONTROL Website label]** van het merk
   * **[!UICONTROL Brand logo]**

  ![](assets/branding_1.png)

* **[!UICONTROL Header parameters of sent emails]** personaliseert wat de ontvangers van uw campagnes te zien krijgen. Deze sectie bevat de volgende velden:

   * **[!UICONTROL Sender (email address)]** met het e-mailadres van het merk
   * **[!UICONTROL Sender (name)]** met de merknaam.
   * **[!UICONTROL Reply to (email address)]** met het e-mailadres waarop de klant kan antwoorden.
   * **[!UICONTROL Reply to (name)]** met de merknaam.
   * **[!UICONTROL Error (email address)]** met het e-mailadres dat moet worden gebruikt bij een fout.

  >[!IMPORTANT]
  >
  >Nadat u de koptekstparameters van de e-mails hebt bijgewerkt, controleert u de geavanceerde instellingen van de sjabloon als de naam en het e-mailadres van de afzender niet zijn gewijzigd in de e-mail die met de sjabloon is gemaakt.

  ![](assets/branding_2.png)

* **[!UICONTROL Brand configs]** definieert de servers die worden gebruikt voor tracering, ook voor het openen van pagina-toegang. Deze sectie bevat de volgende velden:

   * **[!UICONTROL Brand subdomain]** verwijst naar de specifieke subdomein-URL voor dit merk, die wordt gevraagd om te worden gedelegeerd aan de Adobe.

  Merk op dat de configuratie voor het volgen, de spiegel, en toepassingsservers in afzonderlijke externe rekeningen verbonden aan het verpletteren wordt opgeslagen. Deze instellingen worden toegepast tijdens de provisioning en mogen niet worden gewijzigd. Als u URL&#39;s wilt weergeven, opent u het tabblad **[!UICONTROL Branding prefixes]** via uw externe account.

  ![](assets/branding_3.png)

* Met het menu **[!UICONTROL Tracking URL configs]** kunt u URL-tracking verbeteren door aanvullende parameters te definiëren voor integratie met hulpprogramma&#39;s voor webanalyse, zoals Adobe Analytics en Googles Analytics.

  Gebruik het menu **[!UICONTROL Additional URL Parameters]** om extra parameters als sleutel-waardeparen samen met hun toepassingsvoorwaarden tot stand te brengen. Elke parameternaam moet uniek en niet leeg zijn en elke parameterwaarde moet niet leeg zijn. De toepassingsvoorwaarde kan leeg zijn, maar geen van deze waarden kan JST-tags bevatten.

  Deze parameters worden toegepast op bijgehouden URL&#39;s die overeenkomen met een domeinnaam die is opgegeven in de **[!UICONTROL List of Domain Names]** . Deze parameters kunnen reguliere expressies bevatten.
