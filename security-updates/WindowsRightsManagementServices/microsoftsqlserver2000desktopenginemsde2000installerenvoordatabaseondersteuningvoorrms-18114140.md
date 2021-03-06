---
TOCTitle: 'Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) installeren voor databaseondersteuning voor RMS'
Title: 'Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) installeren voor databaseondersteuning voor RMS'
ms:assetid: 'c9b9cd08-98c4-424f-b3fc-d685f57c002e'
ms:contentKeyID: 18114140
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747667(v=WS.10)'
---

Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) installeren voor databaseondersteuning voor RMS
====================================================================================================

Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) installeren voor databaseondersteuning voor RMS
----------------------------------------------------------------------------------------------------

#### Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) installeren voor databaseondersteuning voor RMS

1.  Meld u aan met een domeinaccount die lid is van de lokale groep Administrators op de server waarop u Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) wilt installeren.

2.  Download MSDE 2000 van de [website van Microsoft](http://www.microsoft.com/) (http://www.microsoft.com/) en sla de toepassing op de gewenste locatie op uw computer op.

3.  Voer het bestand MSDE2000A.exe uit om het installatiepakket van MSDE 2000 uit te pakken en in een map op te slaan. Deze map krijgt standaard de naam MSDERelA, maar u kunt ook een andere naam opgeven.

4.  Open een opdrachtregel en ga naar de locatie waarop u de installatie van MSDE 2000 hebt opgeslagen.

5.  Als u Microsoft SQL Server 2000 Desktop Engine wilt installeren met de juiste configuratie, zodat de toepassing kan worden gebruikt in combinatie met RMS, typt u de volgende opdracht. Vervang hierbij *wachtwoord* door het sterke wachtwoord dat u wilt gebruiken:

    **Setup.exe /i setup\\sqlrun10.msi INSTANCENAME=RMS DISABLEAGENTSTARTUP=1 SAPWD=***wachtwoord*

    | ![](images/Cc747667.Important(WS.10).gif)Belangrijk                                                                                                                                                                                                                   |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | De MSDE-service moet worden gestart nadat hij is geïnstalleerd. U kunt de service starten vanuit **Services** in het **Configuratiescherm**. Het wordt aanbevolen de service zo te configureren dat deze automatisch start, zodat de MSDE-database altijd beschikbaar is als RMS wordt uitgevoerd. |

Richt RMS pas in op een server nadat u een database hebt geïnstalleerd ter ondersteuning van de RMS-configuratiedatabase.

Het wordt aangeraden Microsoft SQL Server Desktop Engine alleen in testomgevingen te gebruiken voor ondersteuning van RMS-databases, omdat Microsoft SQL Server Desktop Engine niet over de noodzakelijke hulpprogramma's beschikt om een database in het gehele bedrijf te kunnen uitvoeren en ondersteunen. Aangezien MSDE externe netwerken niet ondersteunt, moet u MSDE op dezelfde server als RMS installeren en kunt u geen extra RMS-servers aan het RMS-cluster toevoegen. In de gebruiksvoorwaarden voor Microsoft SQL Server Desktop Engine wordt aangegeven dat u hulpprogramma's voor SQL Server-clients niet kunt gebruiken voor het bewerken van een Microsoft SQL Server Desktop Engine-database. Door deze beperking kunt u geen back-up maken van de RMS-configuratiedatabase en deze herstellen en geen logboekgegevens weergeven of gegevens wijzigen die in de configuratiedatabase zijn opgeslagen.
