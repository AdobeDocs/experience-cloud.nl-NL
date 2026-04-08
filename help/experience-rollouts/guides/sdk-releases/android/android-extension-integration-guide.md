---
title: Experience Rollout-extensie voor Android-integratiehandleiding
description: Leer hoe u de Experience Rollout-extensie kunt integreren met de Adobe Experience Platform Mobile SDK op Android.
source-git-commit: fcb1d36fc92b3954a902d818a98f579672c577e9
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 2%

---


# Experience Rollout-extensie voor Android {#android-extension-integration-guide}

In deze handleiding wordt beschreven hoe u de Experience Rollout-extensie kunt integreren met de Adobe Experience Platform Mobile SDK op Android.

## Vereisten {#prerequisites}

Voordat u de Extension Experience Rollout-extensie implementeert, moet u controleren of u beschikt over:

* Een mobiel bezit dat in [&#x200B; wordt gevormd de Inzameling van Gegevens van Adobe Experience Platform &#x200B;](https://experience.adobe.com/#/data-collection)
* De Experience Rollout-extensie die is geïnstalleerd en geconfigureerd in uw mobiele eigenschap
* Een Adobe Experience Cloud-organisatie-id
* Minimale SDK: API 21 (Android 5.0 Lollipop)

## Afhankelijkheden van extensies {#extension-dependencies}

Voor de Experience Rollout-extensie zijn de volgende Adobe Experience Platform-extensies vereist:

| Extensie | Beschrijving | Vereist |
|---|---|---|
| Mobiele kern | Biedt kernfunctionaliteit, zoals configuratie en gebeurtenisverwerking | Ja |
| Levenscyclus | Verzamelt levenscyclus- en sessiegegevens van toepassingen voor de Mobile SDK | Ja |
| Edge Network | Maakt communicatie met Adobe Experience Platform Edge Network mogelijk | Ja |
| Edge-identiteit | Gebruikersidentiteit voor Edge Network beheren | Ja |

Zorg ervoor dat deze extensies zijn geïnstalleerd in de mobiele eigenschap Gegevensverzameling en zijn opgenomen in uw toepassingsafhankelijkheden.

## De extensie Experience Rolout configureren in Gegevensverzameling {#configure}

### De extensie installeren {#install-extension}

1. Login aan [&#x200B; de Inzameling van Gegevens van Adobe Experience Platform &#x200B;](https://experience.adobe.com/#/data-collection).
1. Selecteer het **lusje van Markeringen** en kies uw mobiel bezit.
1. Navigeer aan **Uitbreidingen** > **Catalogus**.
1. Onderzoek naar **de uitbreiding van de Uitvoer van de Ervaring** en selecteer **installeer**.
1. Configureer de extensie-instellingen:

   | Instelling | Beschrijving |
   |---|---|
   | Sandbox | De Adobe Experience Platform-sandbox met uw Experience Rollout-configuratie |
   | Toepassings-id | Een unieke id voor uw toepassing in Experience Rollout |
   | Dataset-id | De Adobe Experience Platform-gegevensset-id voor de analytische gebeurtenisgegevens |

1. Selecteer **sparen**.
1. Volg het [&#x200B; het publiceren proces &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/tags/publish/overview) om uw configuratie bij te werken.

### Bestand-id van omgeving ophalen {#environment-file-id}

1. In uw mobiel bezit, navigeer aan **Milieu&#39;s**.
1. Selecteer het bakpictogram onder **installeer** kolom voor uw milieu.
1. In de **Mobiele dialoog van de Installatieinstructies**, kopieer **identiteitskaart van het Dossier van het Milieu**.

## De Extension Experience Rolout toevoegen aan uw app {#add-to-app}

### Afhankelijkheden toevoegen {#add-dependencies}

Voeg de afhankelijkheden van Mobile SDK toe aan uw project. De Experience Rollout-extensie vereist Mobile Core en de Edge-gerelateerde extensies die hieronder worden vermeld.

#### Werken met slede met BOM (aanbevolen) {#gradle-bom}

Voeg de volgende afhankelijkheden toe aan het `build.gradle.kts` -bestand van uw app:

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Experience Rollout extension
    implementation("com.adobe.marketing.mobile:rollout")
}
```

#### Gradle gebruiken (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Experience Rollout extension
    implementation 'com.adobe.marketing.mobile:rollout'
}
```

>[!IMPORTANT]
>
>Voor productietoepassingen, adviseert Adobe het gebruiken van expliciete versienummers in plaats van dynamische versies. Zie [&#x200B; het Leiden de gebiedsdelen van de Gradle &#x200B;](https://docs.gradle.org/current/userguide/dependency_management.html) voor meer informatie.

### Machtigingen toevoegen {#add-permissions}

Voeg de volgende machtigingen toe aan uw `AndroidManifest.xml` -bestand:

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### De SDK initialiseren {#initialize-sdk}

Initialiseer de Mobile SDK in uw `Application` -klasse voordat u API&#39;s van de Experience Rollout-extensie aanroept. Gebruik de Omgevingsbestand-id van uw mobiele eigenschap met `MobileCore.initialize` , zodat de toepassing de rollout-instellingen ophaalt die u in Gegevensverzameling hebt gepubliceerd.

#### MobileCore.initialize gebruiken {#mobile-core-initialize}

Deze API is beschikbaar vanaf Android BOM versie 3.8.0 en registreert automatisch extensies en schakelt levenscyclustracering in.

>[!IMPORTANT]
>
>Gebruik `LoggingMode.ERROR` alleen voor productie-apps. Gebruik `DEBUG` of `VERBOSE` niet in releasebuilds.

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### De klasse Application registreren {#register-application}

Registreer uw `Application` -klasse in `AndroidManifest.xml` :

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## Evaluatiecontext {#evaluation-context}

`FeatureEvaluationContext` bevat doelkenmerken (gebruikt voor overeenkomende uitrolregels) en optionele id (gebruikt voor analyses).

| Methode | Vereist | Beschrijving |
|---|---|---|
| `withIdentity(namespace, id)` | Nee | Eerste argument: identiteit namespace (zie [&#x200B; Identiteitsnaamruimten van Adobe &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/identity/features/namespaces)). Tweede argument: identiteitswaarde. Omvat dit wanneer u die namespace en identiteitskaart in analyses voor deze evaluatie wordt vertegenwoordigd. Als deze optie niet wordt opgegeven, wordt standaard ECID gebruikt. Dit wordt niet gebruikt om de besluiten van de eigenschapenactivering te drijven. |
| `withAttributes(map)` | Nee | `Map<String, List<String>>`. De sleutel is de naam van het contextkenmerk dat wordt gebruikt door de regels voor het uitvoeren van de functie (bijvoorbeeld `locale` , `platform` , `appVersion` , `deviceType` ). Waarde is de lijst met kandidaat-kenmerkwaarden voor die toets voor de huidige gebruiker/sessie (bijvoorbeeld `["en_US"]` of `["phone"]` ). |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.rollout.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID"),
    "appVersion" to listOf("3.0.0")
)

val ctx = FeatureEvaluationContext.builder()
    .withIdentity("Email", "customer@example.com")
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.rollout.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));
attrs.put("appVersion", Arrays.asList("3.0.0"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withIdentity("Email", "customer@example.com")
        .withAttributes(attrs)
        .build();
```

### Voorbeeld van kenmerken voor doelframes {#sample-attributes}

| Kenmerk | Beschrijving | Voorwaarden |
|---|---|---|
| `locale` | Landinstelling/taal van gebruiker | `["en_US"]`, `["fr_FR"]` |
| `platform` | Platform-id | `["ANDROID"]` |
| `appVersion` | Toepassingsversie | `["3.0.0"]` |
| `deviceType` | Apparaattype | `["phone"]`, `["tablet"]` |

## API-referentie {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` geeft aan of een functie Experience Rollout voor de gegeven context in- of uitgeschakeld is. Geef `featureKey` door, een `FeatureEvaluationContext` (optioneel voor kenmerken die voor activering zijn bedoeld en een optionele identiteit voor analyses) en een callback. Zie [&#x200B; context van de Evaluatie &#x200B;](#evaluation-context).

**Handtekening**

*Kotlin*

```kotlin
Rollout.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Rollout.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**Parameters**

| Parameter | Type | Beschrijving |
|---|---|---|
| `featureKey` | String | Functietoets die moet worden geëvalueerd in Experience Rollout |
| `evaluationContext` | FeatureEvaluationContext | Voeg indien nodig doelkenmerken en optionele identiteit voor analyses toe. Gebruik `FeatureEvaluationContext.builder().build()` voor een lege context. Zie [&#x200B; context van de Evaluatie &#x200B;](#evaluation-context). |
| `callback` | AdobeCallback&lt;Boolean> | Wordt aangeroepen met `true` als de functie is ingeschakeld, anders `false` . U kunt `AdobeCallbackWithError<Boolean>` ook doorgeven om `fail(...)` te verwerken. |

**Voorbeelden**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.rollout.Rollout

Rollout.isFeatureEnabled(
    "new-checkout-experience",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                showNewCheckout()
            } else {
                showDefaultCheckout()
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.rollout.Rollout;

Rollout.isFeatureEnabled(
    "new-checkout-experience",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                showNewCheckout();
            } else {
                showDefaultCheckout();
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature` retourneert de geëvalueerde functielading voor de opgegeven context. Gebruik deze API wanneer u meer dan ingeschakeld/uitgeschakeld nodig hebt en metagegevens of waarden van functies wilt.

**Handtekening**

*Kotlin*

```kotlin
Rollout.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Rollout.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**Parameters**

| Parameter | Type | Beschrijving |
|---|---|---|
| `featureKey` | String | Functietoets die moet worden geëvalueerd in Experience Rollout |
| `evaluationContext` | FeatureEvaluationContext | Voeg indien nodig doelkenmerken en optionele identiteit voor analyses toe. Gebruik `FeatureEvaluationContext.builder().build()` voor een lege context. Zie [&#x200B; context van de Evaluatie &#x200B;](#evaluation-context). |
| `callback` | AdobeCallback&lt;FeatureEvaluationResult> | Wordt aangeroepen met de geëvalueerde functielading; is mogelijk `null` wanneer de functie niet wordt gevonden. U kunt `AdobeCallbackWithError<FeatureEvaluationResult>` ook doorgeven om `fail(...)` te verwerken. |

**Reactie**

*FeatureEvaluationResult*

| Veld | Type | Beschrijving |
|---|---|---|
| `id` | Int | Numerieke functie-id |
| `key` | String | Functietoets |
| `releaseKey` | Tekenreeks? | Geen sleutel voor deze functie indien beschikbaar |
| `meta` | Tekenreeks? | Metagegevens van functies als een JSON-tekenreeks, indien beschikbaar |
| `analyticsParam` | AnalyticsParam? | Details van analyse voor de geëvalueerde functie |

*AnalyticsParam*

| Veld | Type | Beschrijving |
|---|---|---|
| `releaseId` | Int | Numerieke release-id |
| `featureId` | Int | Numerieke functie-id |
| `variantId` | Tekenreeks? | Variant-id |

**Voorbeelden**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.rollout.FeatureEvaluationResult
import com.adobe.marketing.mobile.rollout.Rollout

Rollout.getFeature(
    "new-checkout-experience",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                applyMetaDrivenExperience(meta)
            } else {
                showFallbackExperience()
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.rollout.FeatureEvaluationResult;
import com.adobe.marketing.mobile.rollout.Rollout;

Rollout.getFeature(
    "new-checkout-experience",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                applyMetaDrivenExperience(meta);
            } else {
                showFallbackExperience();
            }
        }
    }
);
```

### refreshCache {#refresh-cache}

Door gebrek, synchroniseert de uitbreiding van de Output van de Ervaring regelmatig de recentste rollout regels en de eigenschappen van de server op een programma u kunt vormen. Als u eerder een update nodig hebt dan de volgende geplande synchronisatie, roept u `refreshCache` aan om te forceren vernieuwt. Doorgaans zijn gevallen van aanmelding na aanmelding of wanneer de status van de app zodanig verandert dat dit van invloed is op het opgeven van doelen.

**Syntaxis**

*Kotlin*

```kotlin
Rollout.refreshCache()
```

*Java*

```java
Rollout.refreshCache();
```

### extensionVersion {#extension-version}

Retourneert de versietekenreeks van de Extension Experience Rollout.

**Syntaxis**

```kotlin
Rollout.extensionVersion(): String
```

**Voorbeeld**

*Kotlin*

```kotlin
val version = Rollout.extensionVersion()
```

*Java*

```java
String version = Rollout.extensionVersion();
```

## API-overzicht {#api-summary}

| API | Retourneert |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext` bevat doelkenmerken voor regels en een optionele identiteit voor analyses. Zie [&#x200B; evaluatie van de Eigenschap &#x200B;](#is-feature-enabled). | Boolean via callback |
| `getFeature(featureKey, evaluationContext, callback)`. Retourneert de geëvalueerde functielading voor de opgegeven context. Zie [&#x200B; getFeature &#x200B;](#get-feature). | FeatureEvaluationResult via callback |
| `refreshCache()` | void |
| `extensionVersion()` | String |

## Zie ook {#see-also}

* [Mobiele toepassingen](../../integrate/mobile-applications.md)
* [Integratiestappen](../../integrate/integration-steps.md)
* [SDK&#39;s](../../integrate/sdks.md)
