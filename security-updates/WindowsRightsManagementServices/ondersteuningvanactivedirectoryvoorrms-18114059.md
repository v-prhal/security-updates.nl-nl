---
TOCTitle: Ondersteuning van Active Directory voor RMS
Title: Ondersteuning van Active Directory voor RMS
ms:assetid: '9589127d-19b3-44f1-b7a1-01992e78218a'
ms:contentKeyID: 18114059
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747604(v=WS.10)'
---

Ondersteuning van Active Directory voor RMS
===========================================

In RMS wordt Active Directory voor de volgende doeleinden gebruikt:

-   **Gebruikers verifiëren.** Active Directory biedt de adreslijstservices die worden gebruikt voor het verifiëren van gebruikers van RMS. Zie '[Beveiligingsmodel van RMS](https://technet.microsoft.com/665db831-366d-4dca-9bb3-cc2912481fe1)' verderop in dit onderwerp voor meer informatie over verificatie en RMS.
-   **Identiteiten van groepslidmaatschappen en afzonderlijke gebruikersaccounts achterhalen.** Active Directory biedt informatie over groepslidmaatschappen waarmee in RMS gebruikslicenties voor door RMS beveiligde inhoud worden verleend wanneer in de uitgiftelicentie rechten aan groepen worden verleend in plaats van aan afzonderlijke gebruikersaccounts. In RMS wordt de verkregen informatie in een lokale cache en in een centrale database met adreslijstservices opgeslagen om het aantal LDAP-query's in Active Directory te beperken. Zie '[Active Directory-cache van RMS](https://technet.microsoft.com/c721a2eb-2fe9-4346-b426-3cc169b97265)' en '[RMS-database met directoryservices](https://technet.microsoft.com/6f6b8586-5d17-4a40-94a3-4dc738195301)' eerder in dit onderwerp voor meer informatie.
-   **De locatie voor het opsporen van de RMS-services opslaan.** Serviceaanvragen, zoals voor een gebruiks- of uitgiftelicentie of een subinschrijving van een licentieserver, moeten worden verstuurd naar de URL voor de uitvoerbare module van de webservice waarmee de aanvraag is goedgekeurd. Alle serviceaanvragen beginnen met een Active Directory-query voor de URL van de serverwebservice (Server.asmx). Met deze webservice wordt vervolgens de betreffende URL voor de serviceaanvraag geleverd. Zie '[RMS-service voor uitgifte en opsporing](https://technet.microsoft.com/336c0d55-fd7f-4aa9-b3e6-bfd6565b1086)' verderop in dit onderwerp voor meer informatie.
