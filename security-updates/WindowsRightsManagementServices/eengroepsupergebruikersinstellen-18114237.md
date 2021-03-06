---
TOCTitle: Een groep supergebruikers instellen
Title: Een groep supergebruikers instellen
ms:assetid: 'f2ef847e-2824-471f-9079-5c343094aba8'
ms:contentKeyID: 18114237
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747798(v=WS.10)'
---

Een groep supergebruikers instellen
===================================

Als u deze procedure wilt uitvoeren, moet u lokaal zijn aangemeld bij de beheerwebsite met een domeingebruikersaccount die lid is van de groep Administrators op de computer die u benadert. Ook leden van de groep Domeinbeheerders kunnen deze procedure uitvoeren. Uit veiligheidsoverwegingen kunt u het beste **Uitvoeren als** gebruiken om deze procedure uit te voeren.

Als u de pagina **Algemeen beheer** wilt openen, klikt u op **Start**, wijst u **Alle programma's** en **Windows RMS** aan en klikt u op **Windows RMS-beheer**.

Voordat een groep kan worden aangewezen als de supergebruikersgroep voor RMS, moet de groep bestaan in Active Directory en moeten de eigenschappen van die groep een e-mailadres omvatten (opgegeven als volledig gekwalificeerde domeinnaam) dat gelijk is aan de accountnaam.

Een groep supergebruikers instellen
-----------------------------------

#### Een groep supergebruikers instellen

1.  Open de pagina **Algemeen beheer** en klik naast de website waarop u een groep supergebruikers wilt instellen op **RMS op deze website beheren**.

2.  Klik in het gedeelte **Beheerkoppelingen** op **Beveiligingsinstellingen**.

3.  Klik in het gedeelte **Supergebruikers** op **Inschakelen** om een groep supergebruikers toe te voegen.

4.  Typ bij **Naam van de supergebruikersgroep** de volledig gekwalificeerde domeinnaam, in de indeling *groepsnaam*@*domeinnaam.com*, van een bestaande groep in dit Active Directory-forest waarvan de leden eigenaarsrechten moeten krijgen voor alle documenten die zijn beveiligd door RMS. Klik daarna op **Opslaan**.

    Als u de rechten voor de groep supergebruikers wilt uitschakelen, klikt u op **Uitschakelen**.

Zie '[De groep supergebruikers gebruiken](https://technet.microsoft.com/0febcb3e-7124-4e51-971a-1013b928d33b)' eerder in dit onderwerp voor meer informatie over het uitvoeren van deze procedure.
