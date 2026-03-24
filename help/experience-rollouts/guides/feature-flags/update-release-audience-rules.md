---
title: Regels voor het publiek van de release bijwerken
description: Leer om publiekscriteria voor een versie in de Rollouts van de Ervaring van Adobe te vormen en bij te werken, met inbegrip van gesteunde regeltypes en hoe te om hen te combineren.
source-git-commit: bb4541dd7a77edadded2edbc9c71905cf70f2e24
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---


# Regels voor het publiek van de release bijwerken {#update-release-audience-rules}

## De publieksinstellingen openen {#access}

Beginnen vormend wie uw versie ontvangt, navigeer aan de publieksmontages in de console:

1. Open uw release in de Experience Rollouts-console.
2. Ga naar het **publiek** lusje.
3. Laat de knevel naast **Regels van het Publiek** toe.
4. Selecteer of om **inclusieregels** toe te voegen (die de versie) of **uitsluitingsregels** (die niet) zouden moeten ontvangen.

## Ondersteunde publiekscriteria {#criteria}

### ID-type {#id-type}

Doelgebruikers op basis van hun accounttype (bijvoorbeeld persoonlijke accounts of ondernemingsaccounts).

### Land {#country}

Doelgebruikers gebaseerd op hun geregistreerde land.

### Gebruikers-id {#user-id}

Het doel specifieke gebruikers door hun uniek gebruikersherkenningsteken (GUID).

### E-mailadres {#email}

Doelgebruikers op hun exacte e-mailadres. Om veelvoudige e-mailadressen tegelijkertijd toe te voegen, selecteer **binnen** van de exploitant drop-down (in plaats van **is**), dan:

* Voer in het tekstvak een lijst met door komma&#39;s gescheiden adressen in, of
* Upload een `.txt` bestand met één adres per regel, of
* Een `.csv` -bestand met de lijst met adressen uploaden

Als uw lijst erg groot is, moet u deze splitsen in kleinere batches.

### E-maildomein {#email-domain}

Stel de focus in op alle gebruikers van wie het e-mailadres tot een specifiek domein behoort (bijvoorbeeld `yourcompany.com` ).

### Client IP {#client-ip}

De gebruikers van het doel die op hun cliëntIP adres worden gebaseerd.

### Percentage {#percentage}

Selecteer een willekeurig percentage van alle gebruikers, inclusief niet-geverifieerde gebruikers.

### Percentage (alleen geverifieerd) {#percentage-auth}

Selecteer een willekeurig percentage alleen geverifieerde gebruikers. Niet-geverifieerde gebruikers worden uitgesloten.

## Meerdere regels combineren {#combining-rules}

U kunt veelvoudige publiekscriteria combineren gebruikend logica AND/OR.

**Voorbeelden:**

* Om slechts ondernemingsrekeningen van een specifiek domein te richten, combineer het **type van identiteitskaart** regel met de **E-mail domein** regel gebruikend EN.
* Om 10% van gebruikers van een specifiek land te richten, combineer de **regel van het Land** met de **3&rbrace; regel van het Percentage &lbrace;.**

Gebruik de pictogrammen **+/-** om voorwaarden toe te voegen of te verwijderen. Als u een voorwaarde wilt dupliceren, selecteert u het dubbele pictogram naast een bestaande regel. Voor complexe genestelde logica, laat **Genestelde Logica** toe en ga een geldige uitdrukking in het tekstvakje in.

## Zie ook {#see-also}

* [Release aanvragen](request-a-release.md)
* [De werkstroom van begin tot einde opheffen](release-workflow-end-to-end.md)
* [Releasestatus](release-states.md)
