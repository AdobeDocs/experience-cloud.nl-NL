---
title: Veelgestelde vragen over releasebeheer
description: Zoek antwoorden op veelgestelde vragen over releasebeheer in Adobe Experience Rollouts.
source-git-commit: d311efb995b20ffc17370d68d57dd84a8605896c
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Veelgestelde vragen over releasebeheer {#release-management-faqs}

## Hoe vraag ik om een release? {#request-release}

Zie [&#x200B; Verzoek om een versie &#x200B;](request-a-release.md) voor het volledige proces en de informatie u moet verstrekken.

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

U kunt veelvoudige regels combineren gebruikend logica AND/OR, met inbegrip van genestelde voorwaarden. Zie [&#x200B; de regels van het de versiepubliek van de Update &#x200B;](update-release-audience-rules.md) voor geleidelijke configuratieinstructies.

## Hoe voeg ik een toepassing aan een versie toe? {#onboard-application}

Nadat de versie wordt gecreeerd, open het in de console en voeg uw toepassing aan de versieconfiguratie toe. De eigenaar van de productrelease voor elke toepassing kan vervolgens de relevante functiemarkeringen toevoegen. Zie [&#x200B; het werkschema van de Versie van begin tot eind &#x200B;](release-workflow-end-to-end.md) voor de volledige opeenvolging.

## Een functie wordt niet geretourneerd voor een gebruiker die hiervoor in aanmerking zou moeten komen. Hoe los ik problemen op? {#troubleshoot}

Voer de volgende stappen uit om fouten op te sporen:

1. **Controle de versiestaat.** De versie moet in **Gepubliceerde** of **Volledige uitrolstatus** zijn om eigenschappen te dienen. Zie {de staten van de Versie 0} [&#128279;](release-states.md).
2. **controleer de toepassing en eigenschapvlag.** Controleer of de functiemarkering is gemaakt voor de juiste toepassing en of de toepassing is gekoppeld aan de juiste release.
3. **Controle dat de eigenschapvlag wordt toegelaten.** Een uitgeschakelde vlag zal niet worden gediend zelfs als de versie actief is.
4. **herzie de publiekscriteria.** Bevestig dat de gebruiker aan alle voorwaarden voldoet die in de publieksregels worden bepaald. Controleer de criteria voor de specifieke versie de eigenschap wordt geassocieerd met tweemaal.

## Zie ook {#see-also}

* [Release aanvragen](request-a-release.md)
* [Regels voor het publiek van de release bijwerken](update-release-audience-rules.md)
* [Releasestatus](release-states.md)
* [De werkstroom van begin tot einde opheffen](release-workflow-end-to-end.md)
