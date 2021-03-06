---
TOCTitle: 'RMS-servers beveiligen'
Title: 'RMS-servers beveiligen'
ms:assetid: '7e6c4d3a-6cfb-4e96-9dda-ead83f961a6e'
ms:contentKeyID: 18114012
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747574(v=WS.10)'
---

RMS-servers beveiligen
======================

U kunt de volgende richtlijnen gebruiken bij het beheren van de gebruikersaccounts en beveiligingsinstellingen op de RMS-servers:

-   In de virtuele mappen van de website waarmee u RMS beheert, zijn DACL's (Discretionary Access Control Lists) opgenomen zodat alleen lokale beheerders toegang hebben. Een lokale beheerder kan nog een beveiligingsgroep maken om de toegang verder te beperken. De beheerder kan leden toevoegen aan en verwijderen uit deze groep en extra ACE's (Access Control Entries) instellen op de beheerwebpagina's.
-   Als u de beveiliging wilt verhogen dient u de DACL-instellingen voor de webpagina Beveiligingsinstellingen (SecurityPolicy.aspx) te wijzigen. De standaard-ACE biedt volledig beheer voor de account waarmee RMS wordt ingericht. Na het inrichten moet u de ACE echter wijzigen in een afzonderlijke of beperkte beveiligingsgroep.
-   Behalve op de rechten en machtigingen voor elke RMS-server moet u speciaal letten op de beveiligingsvereisten van de configuratiedatabase, aangezien deze essentieel zijn voor de beveiliging van de volledige implementatie. Zie '[De configuratiedatabase beveiligen](https://technet.microsoft.com/e023b96f-81d0-45fb-8cc5-becaf6d47ae1)' verderop in dit onderwerp voor meer informatie.

Voor meer informatie over de beveiliging van Microsoft SQL Server™ verwijzen wij u naar de webpagina **SQL Server Security** op de [website van Microsoft](http://www.microsoft.com/(http://www.microsoft.com/)).

Download de beveiligingshandleiding van Windows Server 2003 via het Microsoft Downloadcentrum op de [website van Microsoft](http://www.microsoft.com/) (http://www.microsoft.com/) voor meer informatie over het beveiligen van computers met het besturingssysteem Microsoft Windows Server 2003.
