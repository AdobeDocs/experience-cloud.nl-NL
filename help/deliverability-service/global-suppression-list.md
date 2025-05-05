---
title: Algemene suppressielijst
description: De algemene suppressielijst detecteren
hide: true
exl-id: 40aef987-52a3-470b-88ca-c716a116bdfc
source-git-commit: b66e2525694c771ebb7ac5190b7259ef5658d81a
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 0%

---

# Algemene suppressielijst {#global-suppression-list}

Een suppressielijst bestaat uit e-mailadressen die klanten van hun leveringen willen uitsluiten, omdat het verzenden naar deze contacten hun verzendende reputatie en leveringspercentages zou kunnen beschadigen. Momenteel houdt de Adobe een bijgewerkte lijst bij van bekende slechte e-mailadressen waarvan is aangetoond dat deze schadelijk zijn voor de service en de reputatie bij het verzenden van berichten, en zorgt deze ervoor dat er geen e-mailberichten aan hen worden bezorgd. Deze lijst wordt beheerd in een globale suppressielijst die over alle klanten van de Adobe gemeenschappelijk is. De adressen en domeinnamen in de globale suppressielijst worden verborgen. Alleen het aantal uitgesloten ontvangers wordt vermeld in de leveringsverslagen.

Het is nu mogelijk om de globale suppressielijst van een interface te beheren die intern beschikbaar is. Deze lijst wordt alleen door de consultants van de leveringszekerheid bijgehouden. De algemene suppressielijst kan e-mail- of domeinadressen bevatten.

## Toegang tot de algemene suppressielijst

Ga naar **[!UICONTROL Gloabl suppression list]** voor toegang tot de gedetailleerde lijst met uitgesloten e-mailadressen en domeinen.

>[!CAUTION]
>
>Toestemmingen om de globale suppressielijst te bekijken, uit te voeren en te beheren hangen van de distributielijst af u aan wordt toegewezen. Meer informatie

Er worden twee tabbladen weergegeven: **[!UICONTROL Email]** en **[!UICONTROL Domain]** .

Er zijn filters beschikbaar waarmee u door de lijst kunt bladeren.

## Voeg adressen en domeinen toe

Er zijn momenteel twee manieren waarop adressen aan de algemene suppressielijst kunnen worden toegevoegd:

* Lijst beheerd door het leveringsteam.
* Lijst verstrekt door de derde dienstverlener Blackbox.

U kunt e-mailadressen of domeinen [ tegelijkertijd ](#add-one-address-or-domain), of [ op bulkwijze ](#upload-csv-file) door een Csv- dossierupload toevoegen.

Hiervoor selecteert u de knop **[!UICONTROL Add email or domain]** en volgt u een van de onderstaande methoden.

### Eén adres of domein toevoegen {#add-one-address-or-domain}

1. Selecteer de optie **[!UICONTROL One by one]** .

1. Kies het adrestype: **[!UICONTROL Email address]** of **[!UICONTROL Domain address]**.

1. Voer het e-mailadres of domein in dat u van uw verzending wilt uitsluiten.

   >[!NOTE]
   >
   >Controleer of u een geldig e-mailadres (zoals abc@company.com) of domein (zoals abc.company.com) invoert.

1. Geef indien nodig een reden op.

   >[!NOTE]
   >
   >Alle afdrukbare ASCII-tekens tussen 32 en 126 zijn toegestaan in dit veld. De volledige lijst kan op [ worden gevonden deze pagina ](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"}  bijvoorbeeld.

1. Klik op **[!UICONTROL Submit]** om te bevestigen.

### Een CSV-bestand uploaden {#upload-csv-file}

1. Selecteer de optie **[!UICONTROL Upload CSV]** .

1. Download de CSV-sjabloon die u wilt gebruiken, inclusief de onderstaande kolommen en indeling:

   ```
   TYPE,VALUE,COMMENT
   EMAIL,abc@somedomain.com,Comment
   DOMAIN,somedomain.com,Comment
   ```

   >[!CAUTION]
   >
   >Wijzig de namen van de kolommen in de CSV-sjabloon niet.
   >
   >De bestandsgrootte mag niet groter zijn dan 1 MB.

1. Vul de CSV-sjabloon in met de e-mailadressen en/of domeinen die u wilt toevoegen aan de suppressielijst.

   >[!NOTE]
   >
   >Alle karakters ASCII die tussen 32 en 126 worden samengesteld worden toegestaan in de **1&rbrace; kolom van de Commentaar &lbrace;.** De volledige lijst kan op [ worden gevonden deze pagina ](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters){target="_blank"}  bijvoorbeeld.

1. Als u klaar bent, sleept u het CSV-bestand en klikt u op **[!UICONTROL Submit]** om het bestand te bevestigen.

>[!NOTE]
>
>Zodra uploaden wordt gedaan, zorg ervoor het door zijn status van de interface te controleren succesvol was. [ leer hoe ](#recent-uploads)

### Status van recente uploads controleren {#recent-uploads}

Klik op de knop **[!UICONTROL Recent uploads]** om de status te controleren van de meest recente CSV-bestanden die u hebt geüpload.

Mogelijke statussen zijn:

* **[!UICONTROL Pending]**: het uploaden van het bestand wordt verwerkt.
* **[!UICONTROL Error]**: Het uploaden van het bestand is mislukt als gevolg van een technisch probleem of een fout in de bestandsindeling.
* **[!UICONTROL Complete]**: het uploadproces voor het bestand is voltooid.

Wanneer tijdens het uploaden sommige adressen niet de juiste indeling hebben, worden ze niet toegevoegd aan de algemene lijst met suppressies.

In dat geval, wanneer uploaden volledig is, wordt het geassocieerd met een rapport. U kunt het downloaden om de aangetroffen fouten te controleren.

## Adressen verwijderen

Als u een adres uit de lijst met wereldwijde onderdrukking wilt verwijderen, gebruikt u de knop **[!UICONTROL Delete]** .

>[!CAUTION]
>
>Adressen of domeinen die automatisch door de derde dienstverlener Blackbox worden toegevoegd kunnen niet door consultants door de interface worden verwijderd. Dit kan alleen via een backend-ticket worden gedaan.
