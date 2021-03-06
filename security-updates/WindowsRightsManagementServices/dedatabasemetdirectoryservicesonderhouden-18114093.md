---
TOCTitle: De database met directoryservices onderhouden
Title: De database met directoryservices onderhouden
ms:assetid: '911a62f2-c1d6-4091-99b0-b53211be27a7'
ms:contentKeyID: 18114093
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747680(v=WS.10)'
---

De database met directoryservices onderhouden
=============================================

De RMS-databaseserver treedt op als host voor de database met directoryservices. Deze database bevat informatie over gebruikers, id's (zoals e-mailadressen), beveiligings-id's (SID's), groepslidmaatschappen en alternatieve id's. Deze gegevens worden opgehaald door LDAP-query's die door de licentieservice van RMS in de algemene catalogus van Active Directory worden uitgevoerd. De gegevens worden vervolgens lokaal in deze database opgeslagen, waardoor de server sneller kan reageren wanneer gebruikers gebruikslicenties aanvragen.

Omdat er vaak gegevens aan deze database worden toegevoegd en eruit worden verwijderd, zal de database snel gefragmenteerd raken. Daarom is het raadzaam regelmatig (elke dag of week) de database op de indexen van alle DRMS\_DirectoryServices-databasetabellen te reorganiseren. Door het opnieuw samenstellen van de indexen zijn de gegevens niet langer gedefragmenteerd. Bij gefragmenteerde gegevens worden de prestaties minder en zelfs de server kan problemen gaan geven als daar niets aan wordt gedaan.

Als u SQL Server als databaseserver gebruikt, kan de database worden onderhouden met de wizard Onderhoud of door uw eigen script met behulp van de SQL Server Agent uit te voeren.

Als bij het herindexeren van de database blijkt dat het transactielogboek onhandelbaar groot is, kunt u de grootte van dat logboek minimaliseren door voordat u gaat indexeren, over te schakelen van de modus Volledig herstel naar de modus Bulkregistratie.
