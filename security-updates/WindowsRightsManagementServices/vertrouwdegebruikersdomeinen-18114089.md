---
TOCTitle: Vertrouwde gebruikersdomeinen
Title: Vertrouwde gebruikersdomeinen
ms:assetid: 'a09b883f-f455-4c46-a4fd-d37b689e1d24'
ms:contentKeyID: 18114089
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747618(v=WS.10)'
---

Vertrouwde gebruikersdomeinen
=============================

Standaard worden in RMS geen gebruikslicenties verleend aan gebruikers met rechtenaccountcertificaten die door een ander gebruikersdomein zijn uitgegeven. Een gebruikersdomein is een RMS-installatie die bestaat uit een basiscertificeringscluster, optionele licentieservers of -clusters en bijbehorende databases.

U kunt RMS zo configureren dat ook dit type aanvragen worden verwerkt. U importeert in dat geval het serverlicentieverleningscertificaat van het andere gebruikersdomein en voegt dit toe aan de lijst met vertrouwde gebruikersdomeinen. Als u dit doet, kunnen gebruikers met accountcertificaten die zijn uitgegeven door het vertrouwde gebruikersdomein, aanvragen voor gebruikslicenties indienen bij uw installatie. Deze gebruikslicenties worden vervolgens verwerkt alsof het aanvragen van interne gebruikers zijn.

| ![](images/Cc747618.note(WS.10).gif)Opmerking                                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Het basiscertificeringscluster wordt automatisch in de lijst met vertrouwde gebruikersdomeinen opgenomen voor alle RMS-servers in dezelfde installatie. |

U kunt instellen dat gebruikers uit verschillende gebruikersdomeinen beveiligde inhoud kunnen delen. Dit wordt beschreven in de volgende voorbeelden:

-   Uw organisatie werkt nauw samen met een andere organisatie aan documenten die u wilt delen en beveiligen. In de andere organisatie wordt RMS eveneens uitgevoerd. Beide organisaties kunnen de RMS-installatie van de andere organisatie toevoegen aan hun lijst met vertrouwde gebruikersdomeinen. Op deze manier kunnen gebruikers uit beide organisaties samen aan beveiligde inhoud werken en deze uitwisselen via internet of een extranet.
-   Er kan slechts één RMS in elk Active Directory-forest zijn geïnstalleerd. In uw organisatie zijn meerdere Active Directory-forests aanwezig en in elk van deze forests wordt RMS uitgevoerd. Gebruikers willen beveiligde inhoud delen met andere gebruikers, ongeacht het forest waarin ze zich bevinden. In dat geval kunt u de RMS-installatie van de andere forests toevoegen aan de lijst met vertrouwde gebruikersdomeinen in elk forest.
-   Gebruikers in uw organisatie werken samen met gebruikers uit een andere organisatie aan vertrouwelijk documenten die moeten worden beveiligd. In de andere organisatie wordt RMS niet uitgevoerd. Gebruikers uit de andere organisatie kunnen .NET Passport-accounts instellen. Vervolgens kunt u .NET Passport toevoegen aan de lijst met vertrouwde gebruikersdomeinen voor uw RMS-installatie. Gebruikers uit beide organisaties kunnen nu met beveiligde inhoud werken die via internet kan worden uitgewisseld.

Zie 'Vertrouwde gebruikersdomeinen toevoegen en verwijderen' en 'Vertrouwensbeleid inschakelen' in 'Een RMS-server beheren' in deze documentatie voor meer informatie over vertrouwde gebruikersdomeinen en stapsgewijze instructies.
