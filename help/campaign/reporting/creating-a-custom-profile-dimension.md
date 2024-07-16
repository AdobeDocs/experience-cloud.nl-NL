---
title: Een profieldimensie maken
description: Leer hoe u een profieldimensie maakt op basis van profielgegevens.
audience: reporting
content-type: reference
level: Intermediate
exl-id: a12dc772-13c7-45ff-9fbf-3dfdd3801eae
source-git-commit: 5da9b29c424f019f3dafc127a41e974017af494c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 2%

---

# Een profieldimensie maken{#creating-a-custom-profile-dimension}

De rapporten kunnen ook worden gecreeerd en worden geleid gebaseerd op profielgegevens die tijdens de ontvankelijke schemauitbreiding worden gecreeerd.

* [Stap 1: Het ontvangende schema uitbreiden](##extend-schema)
* [Stap 2: Uw nieuwe aangepaste veld koppelen](#link-custom)
* [Stap 3: Creeer een dynamisch rapport aan filterontvangers met de profieldimensie](#create-report)

## Stap 1: Het ontvangende schema uitbreiden {#extend-schema}

Voer de onderstaande stappen uit om een nieuw profielveld toe te voegen.

1. Navigeer naar de map **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]** in de Verkenner.

   ![](assets/custom_field_1.png)

1. Identificeer uw douane ontvankelijk schema en selecteer het. Als u nog niet ingebouwde nms hebt uitgebreid:ontvankelijk schema, verwijs naar [ deze procedure ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/extend-schema).

1. Voeg uw douanegebied aan de schemaredacteur toe.

   Bijvoorbeeld, om een douane gebied van de Loyalty in uw ontvangend schema toe te voegen:

   ```
   <attribute label="Loyalty" name="loyalty" type="string"/>
   ```

   ![](assets/custom_field_2.png)

1. Klik op **[!UICONTROL Save]**.

1. Vervolgens identificeert u het aangepaste bredeLogRcp-schema en selecteert u dit. Als u nog niet het ingebouwde het logboekschema van de Levering hebt uitgebreid, verwijs naar [ deze procedure ](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/extend-schema).

1. Voeg hetzelfde aangepaste veld als het schema Ontvanger toe aan de schema-editor.

   ![](assets/custom_field_3.png)

1. Klik op **[!UICONTROL Save]**.

1. Als u de wijzigingen wilt toepassen die in de schema&#39;s zijn aangebracht, start u de wizard Database bijwerken via **[!UICONTROL Tools]** > **[!UICONTROL Advanced]** > **[!UICONTROL Update database structure]** en voert u de databasestructuur bijwerken uit. [Meer informatie](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/shemas-forms/update-database-structure)

   ![](assets/custom_field_4.png)

Uw nieuwe profielveld kan nu worden gebruikt en geselecteerd door uw ontvangers.

## Stap 2: Uw nieuwe aangepaste veld koppelen {#link-custom}

>[!NOTE]
>
> U kunt maximaal 20 douanegebied aan Dynamisch rapport toevoegen.

Nu uw profielgebied wordt gecreeerd, moeten wij het met de overeenkomstige Dynamische het melden afmeting verbinden.

Alvorens het logboek met ons profielgebied uit te breiden, zorg ervoor dat het PII venster werd toegelaten om PII gegevens naar dynamisch rapport te kunnen verzenden. Raadpleeg [deze pagina](pii-agreement.md) voor meer informatie.

1. Ga naar de map **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]** > **[!UICONTROL Additional reporting field]** in de Verkenner.

   ![](assets/custom_field_5.png)

1. Klik op **[!UICONTROL New]** om de corresponderende dimensie voor dynamische rapportage te maken.

1. Selecteer **[!UICONTROL Edit expression]** en blader door het schema Ontvanger om het eerder gemaakte profielveld te zoeken.

   ![](assets/custom_field_6.png)

1. Klik op **[!UICONTROL Finish]**.

1. Typ uw dimensie **[!UICONTROL Label]**, zichtbaar in Dynamische rapportage en klik op **[!UICONTROL Save]** .

   ![](assets/custom_field_7.png)

Uw profielveld is nu beschikbaar als profieldimensie in uw rapporten. Als u de profieldimensie wilt verwijderen, selecteert u deze en klikt u op het pictogram **[!UICONTROL Delete]** .

Nu het ontvankelijke schema met dit profielgebied is uitgebreid en uw douanedimensie gecreeerd, kunt u beginnen ontvangers in leveringen te richten.

## Stap 3: Creeer een dynamisch rapport aan filterontvangers met de profieldimensie {#create-report}

Nadat u de levering hebt verzonden, kunt u rapporten afbreken aan de hand van uw profieldimensie.

1. Selecteer op het tabblad **[!UICONTROL Reports]** een rapport uit de doos of klik op de knop **[!UICONTROL Create]** om een rapport helemaal opnieuw te beginnen.

   ![](assets/custom_field_8.png)

1. Klik in de categorie **[!UICONTROL Dimensions]** op **[!UICONTROL Profile]** en sleep de profieldimensie naar de vrije-vormtabel.

   ![](assets/custom_field_9.png)

1. Sleep alle metriek om te beginnen met het filteren van de gegevens.

1. Sleep indien nodig een visualisatie naar de werkruimte.

