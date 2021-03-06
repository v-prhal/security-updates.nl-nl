---
TOCTitle: 'Logboekregistratie in- of uitschakelen'
Title: 'Logboekregistratie in- of uitschakelen'
ms:assetid: '8e672f95-566f-4070-9a2a-2f70f087148f'
ms:contentKeyID: 18114078
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747674(v=WS.10)'
---

Logboekregistratie in- of uitschakelen
======================================

Als u deze procedure wilt uitvoeren, moet u lokaal zijn aangemeld bij de beheerwebsite met een domeingebruikersaccount die lid is van de groep Administrators op de computer die u benadert. Ook leden van de groep Domeinbeheerders kunnen deze procedure uitvoeren. Uit veiligheidsoverwegingen kunt u het beste **Uitvoeren als** gebruiken om deze procedure uit te voeren.

Als u de pagina **Algemeen beheer** wilt openen, klikt u op **Start**, wijst u **Alle programma's** en **Windows RMS** aan en klikt u op **Windows RMS-beheer**.

De RMS-server moet een verbinding hebben met de databaseserver, en de databaseservice moet worden uitgevoerd voordat logboekregistratie wordt gestart. Als Message Queuing de logboekgegevens niet aan de database kan leveren, worden de gegevens in de wachtrij gehouden op de vaste schijf van de RMS-server. Dit blijft zo tot er op de server geen opslagruimte meer is. RMS geeft in deze situatie geen foutmelding, omdat de functie is bedoeld om logboekregistratie te ondersteunen wanneer de verbinding met de SQL-server is onderbroken.

Logboekregistratie in- of uitschakelen
--------------------------------------

#### Logboekregistratie in- of uitschakelen

1.  Open de pagina **Algemeen beheer** en klik naast de website waarop u de logboekregistratie wilt in- of uitschakelen op **RMS op deze website beheren**.

2.  Klik in het gedeelte **Beheerkoppelingen** op **Logboekinstellingen**.

3.  Schakel in het gedeelte **Logboekserver en -database** het selectievakje **Logboekregistratie inschakelen** in en klik op **Bijwerken**.

    Als u de logboekregistratie wilt uitschakelen, schakelt u het selectievakje uit en klikt u op **Bijwerken**.

Zie '[Logboekregistratie in- en uitschakelen](https://technet.microsoft.com/50ccd827-2d39-41e7-a395-3d5f5836869b)' eerder in dit onderwerp voor meer informatie over het uitvoeren van deze procedure.
