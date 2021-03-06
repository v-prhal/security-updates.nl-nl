---
TOCTitle: De inrichting van RMS ongedaan maken
Title: De inrichting van RMS ongedaan maken
ms:assetid: '9fa63daa-5fb9-4afd-8371-b38248619857'
ms:contentKeyID: 18114105
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747706(v=WS.10)'
---

De inrichting van RMS ongedaan maken
====================================

Als u deze procedure wilt uitvoeren, moet u lokaal zijn aangemeld bij de beheerwebsite met een domeingebruikersaccount die lid is van de groep Administrators op de computer die u benadert. Ook leden van de groep Domeinbeheerders kunnen deze procedure uitvoeren. Uit veiligheidsoverwegingen kunt u het beste **Uitvoeren als** gebruiken om deze procedure uit te voeren.

Als u de pagina **Algemeen beheer** wilt openen, klikt u op **Start**, wijst u **Alle programma's** en **Windows RMS** aan en klikt u op **Windows RMS-beheer**.

Wanneer u de inrichting van een server ongedaan maakt, wordt deze verwijderd uit de ClusterServer-tabel van de configuratiedatabase. Wanneer u de inrichting van de laatste server in een cluster ongedaan maakt, wordt de database met adreslijstservices verwijderd van de SQL-server. Wanneer u de inrichting van de laatste basiscertificeringsserver in een cluster ongedaan maakt, moet u de registratie van het serviceverbindingspunt voor de certificering handmatig ongedaan maken. Als u de inrichting en installatie ongedaan maakt, wordt het serviceverbindingspunt niet automatisch verwijderd uit Active Directory.

Als u de installatie de van basiscertificeringsserver ongedaan maakt voordat u deze hebt ingericht, ontvangt u een waarschuwing dat de inrichting van de site nog niet ongedaan is gemaakt en dat het serviceverbindingspunt niet uit Active Directory zal worden verwijderd. Als u op **Ja** klikt om door te gaan, wordt de inrichting van de site ongedaan gemaakt. Als u de installatie ongedaan maakt, wordt het serviceverbindingspunt niet automatisch verwijderd uit Active Directory.

De inrichting van RMS ongedaan maken
------------------------------------

#### De inrichting van RMS ongedaan maken

1.  Meld u aan bij de server waarop u de inrichting van Windows RMS ongedaan wilt maken.

2.  Open de pagina **Algemeen beheer**.

3.  Klik op **RMS van deze website verwijderen** naast de website waarop RMS is ingericht en klik op **OK**.

4.  Klik op de webpagina met het RMS-serviceverbindingspunt op **Registratie van URL ongedaan maken** om de registratie van de verbinding voor de certificeringsservice te verwijderen uit Active Directory.
