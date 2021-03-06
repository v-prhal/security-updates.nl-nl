---
TOCTitle: Beveiliging tijdens het installeren van RMS
Title: Beveiliging tijdens het installeren van RMS
ms:assetid: '0a3d40b2-f27e-4e63-baff-a9c8433f5f91'
ms:contentKeyID: 18113869
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720192(v=WS.10)'
---

Beveiliging tijdens het installeren van RMS
===========================================

Het installatieprogramma van RMS gebruikt de referenties van de aangemelde gebruiker om RMS-bestanden te installeren en configureren. De beheerder die de installatie uitvoert, moet zich aanmelden met een gebruikersaccount die deel uitmaakt van de lokale groep Beheerders. Tenzij er slechts één computer wordt geïnstalleerd, moet deze account tevens zijn ingesteld als domeingebruikersaccount.

Tijdens de installatieprocedure wordt de Windows Installer-service (Msiexec.exe) gestart. Voor deze service wordt het gebruikerstoken van de bovenliggende service gebruikt. Wanneer door de aangemelde gebruiker aangepaste acties zijn uitgevoerd, wordt de identiteit van deze gebruiker door de service Msiexec.exe gebruikt, ongeacht of het proces is gestart vanuit een browser of vanaf de opdrachtregel.

Met het installatieprogramma van RMS worden de volgende taken uitgevoerd:

-   Bestanden worden naar de map C:\\Program Files\\RMS gekopieerd. Deze map is doorgaans toegankelijk voor de groepen Administrators en Hoofdgebruikers. Tijdens de installatie kunt u de stations- en bestandslocatie configureren.
-   De inrichtingswebsite, RMS-beheer, wordt standaard op poort 5720 gemaakt. Op deze website wordt verwezen naar de geïnstalleerde bestanden.
-   Er wordt een toepassingengroep, WMCSProvisioningAppPool, gemaakt die aan de website RMS-beheer wordt gekoppeld. De serviceaccount die door deze toepassingengroep wordt gebruikt, is de serviceaccount NetworkService.
-   Er worden prestatiemeteritems geïnstalleerd.
-   Aan de RMS-servicegroep worden voor de volgende registersleutel lees- en schrijfmachtigingen toegewezen.
    Op computers met de 32-bits versie van Windows Server 2003
    `HKEY_LOCAL_MACHINE\Software\Microsoft\DRMS\1.0`
    Op computers met de 64-bits versie van Windows Server 2003
    `HKEY_LOCAL_MACHINE\Software\WOW6432Node\Microsoft\DRMS\1.0`
