---
TOCTitle: Het serviceverbindingspunt registreren
Title: Het serviceverbindingspunt registreren
ms:assetid: '446d83ec-3224-45e2-9697-625e7db338f3'
ms:contentKeyID: 18113911
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720260(v=WS.10)'
---

Het serviceverbindingspunt registreren
======================================

Met het serviceverbindingspunt voor RMS wordt de verbindings-URL voor de service aangeduid voor de clients met RM-ondersteuning in uw organisatie. Zonder een geldig serviceverbindingspunt kunnen clients RMS niet opsporen om gebruikslicenties, uitgiftelicenties of rechtenaccountcertificaten aan te vragen.

U kunt de serviceverbindingspunt-URL voor uw basiscertificeringscluster registreren via de pagina **Serviceverbindingspunt** voor RMS op de beheerwebsite. U kunt de serviceverbindingspunt-URL ook van de pagina **Serviceverbindingspunt** verwijderen als u de URL opnieuw wilt instellen. Als u een serviceverbindingspunt-URL wilt registreren of verwijderen, moet u zijn aangemeld met een geldige domeingebruikersaccount waarmee u een containerobject onder de container Services kunt maken.

Onder de container Service in Active Directory wordt een nieuw containerobject met de naam RightsManagementServices gemaakt. Onder deze container wordt een object voor het serviceverbindingspunt met de naam MSRMRootCluster gemaakt. Voor het trefwoordenkenmerk van dit object zijn twee waarden ingesteld:

-   MSRMRootCluster
-   1.0

Dit zijn de kenmerken die door clients en andere servers worden gebruikt om de basiscertificeringscluster-URL te vinden in Active Directory. Het kenmerk serviceBindingInformation van het serviceverbindingspuntobject bevat de basiscertificeringscluster-URL in de notatie http://*clusternaam*/\_wmcs/Certification.
