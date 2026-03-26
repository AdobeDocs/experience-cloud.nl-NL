---
audience: user
user-guide-title: Adobe Experience Rollouts
user-guide-description: Leer hoe u Adobe Experience Rollouts kunt gebruiken om functiemarkeringen, gecontroleerde rollouts en doelgerichte releases in uw toepassingen te beheren.
source-git-commit: c654ca1507abcefcff84cef9f99830042939805d
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 1%

---


# Adobe Experience Rollouts {#experience-rollouts}

+ [Overzicht](home.md)
+ Aan de slag {#get-started}
   + [Inleiding tot Experience Rollouts](getting-started/introduction.md)
   + [Waarom Experience Rollouts gebruiken](getting-started/why-use-experience-rollouts.md)
   + [Modus Experience Rolouts](getting-started/experience-rollouts-modes.md)
+ Concepten {#concepts}
   + [Wat is een functiemarkering](concepts/what-is-a-feature-flag.md)
   + [Functiemarkeringen om functies in en uit te schakelen](concepts/feature-flags-to-enable-disable-features.md)
   + [Functiegroepen om meerdere functies te beheren](concepts/feature-groups-to-control-multiple-features.md)
   + [Begrip van releasebeheer](concepts/concept-of-release-management.md)
   + [Beheer vrijgeven in Experience Rollouts](concepts/release-management.md)
   + [Geleidelijke rollout](concepts/gradual-rollout.md)
+ Handleidingen {#guides}
   + Aan de slag met de console {#console}
      + [Aanmelden bij de console Experience Rollouts](guides/console/log-in-to-the-console.md)
      + [Uw sandbox selecteren](guides/console/environments-overview.md)
      + [Toegang aanvragen](guides/console/request-access.md)
   + Toepassingen {#applications}
      + [Toepassingen beheren](guides/applications/manage-applications.md)
      + [Aan boord van uw toepassing](guides/applications/onboard-your-application.md)
   + Integreer de rollouts van Ervaring {#integrate}
      + [Integreer Experience Rollouts in uw app](guides/integrate/integrating-in-your-app.md)
      + [Opstartgids](guides/integrate/startup-guide.md)
      + [Bureaubladtoepassingen](guides/integrate/desktop-applications.md)
      + [Mobiele toepassingen](guides/integrate/mobile-applications.md)
      + [Webtoepassingen](guides/integrate/web-applications.md)
      + [Webservices](guides/integrate/web-services.md)
      + [SDK&#39;s](guides/integrate/sdks.md)
      + [Integratiestappen](guides/integrate/integration-steps.md)
      + [Abonneren op de API-toepassing in Adobe Developer Console](guides/integrate/subscribe-to-api-application.md)
   + Functiemarkeringen {#feature-flags}
      + [Functies en functiegroepen](guides/feature-flags/features-feature-groups-releases.md)
      + [De eerste functiemarkering maken](guides/feature-flags/create-your-first-feature-flag.md)
      + [Een functie instellen die geleidelijk moet worden geïmplementeerd](guides/feature-flags/set-feature-gradual-rollout.md)
      + [Een functiegroep maken](guides/feature-flags/create-a-feature-group.md)
      + [Een functiegroep instellen die geleidelijk moet worden geïmplementeerd](guides/feature-flags/set-feature-group-gradual-rollout.md)
      + [A/B testen met functiemarkeringen](guides/feature-flags/a-b-testing.md)
      + [Veelgestelde vragen over releasebeheer](guides/feature-flags/release-management-faqs.md)
      + [Analyse](guides/feature-flags/analytics.md)
      + [Schema](guides/feature-flags/schedule.md)
   + Criteria voor het publiek {#audience}
      + [Publiek in functiemarkeringen en functiegroepen](guides/audience/audience-in-feature-flags-and-feature-groups.md)
      + [Context gebruiken in publieksregels](guides/audience/using-context-in-audience-rules.md)
      + [Complexe publieksregels](guides/audience/complex-rules.md)
      + [Enterprise-org-gegevens gebruiken in publieksregels](guides/audience/using-enterprise-org-data.md)
      + [Percentageregels toevoegen aan publiekscriteria](guides/audience/adding-percentage-rules.md)
      + [De regel van het publiek met cliëntIP contextvariabele](guides/audience/clientip-rule.md)
   + Workflows tussen omgevingen {#cross-environment}
      + [Concept tussen milieu en milieu](guides/cross-environment/cross-environment-concept.md)
      + [Omgevingen koppelen aan een toepassing](guides/cross-environment/associate-environments.md)
      + [Functievlaggen weergeven in verschillende omgevingen](guides/cross-environment/view-feature-flags-across-environments.md)
      + [Markeringen voor importfuncties](guides/cross-environment/import-feature-flags.md)
   + Ondersteuning {#support}
      + [Problemen oplossen](guides/support/troubleshooting.md)
      + [Ondersteuning](guides/support/get-support.md)
      + [Contact opnemen met ondersteuning](guides/support/contact-support.md)
   + SDK-releases {#sdk-releases}
      + Java SDK {#java-sdk}
         + [Integratiehandleiding voor Java SDK](guides/sdk-releases/java/java-sdk-integration-guide.md)
         + [Opmerkingen bij de release Java SDK](guides/sdk-releases/java/java-sdk-release-notes.md)
      + Node.js SDK {#nodejs-sdk}
         + [Node.js SDK Integration guide](guides/sdk-releases/nodejs/nodejs-sdk-integration-guide.md)
         + [Opmerkingen bij de release Node.js SDK](guides/sdk-releases/nodejs/nodejs-sdk-release-notes.md)
      + [SDK-benchmarking](guides/sdk-releases/java-sdk-benchmarking.md)
+ Functie-API {#feature-api}
   + [GET Feature API V3](feature-api/get-feature-api-v3.md)
   + [GET Feature API V2](feature-api/get-feature-api-v2.md)
+ Beheer-API {#management-api}
   + [Overzicht van API&#39;s voor functiebeheer](management-api/feature-management-apis-overview.md)
   + [API voor kenmerkvlaggen](management-api/feature-flags-management-api.md)
   + [API voor beheer van functiegroepen](management-api/feature-group-management-api.md)
   + [Beheer-API&#39;s vrijgeven](management-api/release-management-apis.md)
   + [Client-id voor een toepassing ophalen](management-api/get-client-id.md)
   + [Kies de gewenste publiekscriteria](management-api/get-audience-criteria.md)
   + [Beheer van patch-API](management-api/management-patch-api.md)
