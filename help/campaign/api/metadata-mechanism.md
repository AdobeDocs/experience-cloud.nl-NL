---
title: Metadatamechanisme
description: Meer informatie over het mechanisme voor metagegevens.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
badge: label="Beperkte beschikbaarheid" type="Informative" url="../campaign-standard-migration-home.md" tooltip="Beperkt tot gemigreerde Campaign Standard-gebruikers"
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: 11c49b273164b632bcffb7de01890c6f9d7ae9c2
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# Metadatamechanisme {#metadata-mechanism}

U kunt de middelmeta-gegevens terugwinnen gebruikend **resourceType** in een verzoek van GET:

`GET /profileAndServices/resourceType/<resourceName>`

De reactie retourneert de hoofdmetagegevens van de bron (alle andere velden zijn beschrijvend of intern):

* De **knoop van de Inhoud** keert de gebieden van het middel terug. Voor elk gebied in de **inhoud** knoop, kunnen wij de volgende gebieden vinden:

   * &quot;apiName&quot;: naam van het kenmerk dat in de API&#39;s wordt gebruikt.
   * &quot;type&quot;: dit is de typedefinitie op hoog niveau (tekenreeks, nummer, koppeling, verzameling, opsomming...).
   * &quot;dataPolicy&quot;: de waarde van het veld moet de gegeven beleidsregels volgen. Als de regel dataPolicy bijvoorbeeld is ingesteld op &#39;email&#39;, moet de waarde een geldige e-mail zijn. Tijdens een PATCH of POST, kan dataPolicy de waarde controleren of de te transformeren waarde wijzigen (smartCase bijvoorbeeld).
   * &quot;categorie&quot;: geeft de categorie van het veld in de zoekeditor.
   * &quot;resType&quot;: dit is het technische type.

     Als &quot;type&quot;met de waarde &quot;verbinding&quot;of &quot;inzameling&quot;wordt voltooid, is de resTarget waarde de naam van het middel dat door de verbinding wordt gericht.
Als het &quot;type&quot;met de waarde &quot;opsomming&quot;wordt voltooid, wordt een &quot;waarden&quot;gebied toegevoegd en elke opsommingswaarde is gedetailleerd in de **waarden** knoop.

* De **Filters** knoop keert URL terug om de bijbehorende filters terug te winnen. Voor meer op filters, verwijs naar [ deze sectie ](filtering.md) sectie.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***verzoek van de Steekproef***

Voer een GET-verzoek uit op de resource.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

De volledige beschrijving van de profielbron wordt geretourneerd.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
