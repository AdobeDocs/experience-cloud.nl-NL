---
title: Veelgestelde vragen over releasebeheer
description: Zoek antwoorden op veelgestelde vragen over releasebeheer in Adobe Experience Rollouts.
exl-id: 802b99bd-85ee-4f4d-afca-88d1297f8782
source-git-commit: 4a3133f014a9bb9d6ed26eb9d9f763db79ce63b3
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# Veelgestelde vragen over releasebeheer {#release-management-faqs}

## Hoe vraag ik om een release? {#request-release}

Contact opnemen met de ondersteuning Rollouts om een release aan te vragen. Geef uw teamnaam, toepassingsgegevens, doelpubliek en de gewenste uitroltijdlijn op.

## Welke publiekscriteria worden gesteund voor versies? {#audience-criteria}

De versies steunen de volgende publieksregels:

* ID-type (accounttype)
* Land
* Gebruikersnaam (GUID)
* E-mailadres (individuele lijst of bulklijst)
* E-maildomein
* Client IP
* Percentage (alle gebruikers)
* Percentage (alleen voor authentiek verklaarde gebruikers)

U kunt veelvoudige regels combineren gebruikend logica AND/OR, met inbegrip van genestelde voorwaarden.

## Hoe voeg ik een toepassing aan een versie toe? {#onboard-application}

Nadat de versie wordt gecreeerd, open het in de console en voeg uw toepassing aan de versieconfiguratie toe. De eigenaar van de productrelease voor elke toepassing kan vervolgens de relevante functiemarkeringen toevoegen.

## Een functie wordt niet geretourneerd voor een gebruiker die hiervoor in aanmerking zou moeten komen. Hoe los ik problemen op? {#troubleshoot}

Voer de volgende stappen uit om fouten op te sporen:

1. **Controle de versiestaat.** De versie moet in **Gepubliceerde** of **Volledige uitrolstatus** zijn om eigenschappen te dienen.
2. **controleer de toepassing en eigenschapvlag.** Controleer of de functiemarkering is gemaakt voor de juiste toepassing en of de toepassing is gekoppeld aan de juiste release.
3. **Controle dat de eigenschapvlag wordt toegelaten.** Een uitgeschakelde vlag zal niet worden gediend zelfs als de versie actief is.
4. **herzie de publiekscriteria.** Bevestig dat de gebruiker aan alle voorwaarden voldoet die in de publieksregels worden bepaald. Controleer de criteria voor de specifieke versie de eigenschap wordt geassocieerd met tweemaal.

## Zie ook {#see-also}

* [Contact opnemen met ondersteuning](../support/contact-support.md)
