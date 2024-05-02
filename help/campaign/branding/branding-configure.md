---
title: Branding
description: Ontdek hoe u uw merk kunt configureren
audience: administration
context-tags: branding,overview;branding,main
role: Admin
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde gebruikers in Campaign Standard"
source-git-commit: 56f2d2ff4b2ba4184629615a14724e6640df6961
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 37%

---

# Brandmerken configureren {#branding-configure}

>[!IMPORTANT]
>
>Merken kunnen niet door eindgebruikers worden gemaakt of gewijzigd. Deze bewerkingen moeten worden uitgevoerd door de technische beheerder van Adobe Campaign. Neem voor elk verzoek contact op met de klantenservice van Adobe.

In Adobe Campaign V8 zijn de merken te vinden in de **[!UICONTROL Administration > Platform > Branding]** -menu.

A **[!UICONTROL Brand]** wordt gedefinieerd door de volgende kenmerken:

* An **[!UICONTROL Identity]**, die uw merk definieert en personaliseert. Deze sectie bevat de volgende velden:

   * **[!UICONTROL Label]** zichtbaar in de interface
   * **[!UICONTROL ID]**
   * **[!UICONTROL Brand name]**
   * **[!UICONTROL Website URL]** en **[!UICONTROL Website label]** van het merk
   * **[!UICONTROL Brand logo]**

  ![](assets/branding_1.png)

* **[!UICONTROL Header parameters of sent emails]** personaliseert wat de ontvangers van uw campagnes te zien krijgen. Deze sectie bevat de volgende velden:

   * **[!UICONTROL Sender (email address)]** met het e-mailadres van het merk.
   * **[!UICONTROL Sender (name)]** met de merknaam.
   * **[!UICONTROL Reply to (email address)]** met het e-mailadres waarop de klant kan antwoorden.
   * **[!UICONTROL Reply to (name)]** met de merknaam.
   * **[!UICONTROL Error (email address)]** met het e-mailadres dat moet worden gebruikt bij een fout.

  >[!IMPORTANT]
  >
  >Nadat u de koptekstparameters van de e-mails hebt bijgewerkt, controleert u de geavanceerde instellingen van de sjabloon als de naam en het e-mailadres van de afzender niet zijn gewijzigd in de e-mail die met de sjabloon is gemaakt.

  ![](assets/branding_2.png)

* **[!UICONTROL Brand configs]** definieert de servers die worden gebruikt voor tracering, ook voor toegang tot de bestemmingspagina. Deze sectie bevat de volgende velden:

   * **[!UICONTROL Brand subdomain]** verwijst naar de opgegeven subdomein-URL die specifiek is voor dit merk en die wordt gevraagd om te worden gedelegeerd aan de Adobe.

  Merk op dat de configuratie voor het volgen, de spiegel, en toepassingsservers in afzonderlijke externe rekeningen verbonden aan het verpletteren wordt opgeslagen. Deze instellingen worden toegepast tijdens de provisioning en mogen niet worden gewijzigd. Als u URL&#39;s wilt weergeven, opent u het dialoogvenster **[!UICONTROL Branding prefixes]** van uw externe account.

  ![](assets/branding_3.png)

<!--![](assets/branding_05.png)-->

<!--
* **[!UICONTROL Tracking URL configs]**, which defines the configuration of the URLs tracking for your brand.

  The additional parameters that allow the links to be tracked on external systems such as Web Analytics tools like Adobe Analytics or Google Analytics are defined here.
-->
