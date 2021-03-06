---
TOCTitle: Een testomgeving instellen
Title: Een testomgeving instellen
ms:assetid: 'cdd96b05-49e2-4b6f-bfae-40b5c028ec66'
ms:contentKeyID: 18114135
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747673(v=WS.10)'
---

Een testomgeving instellen
==========================

RMS wordt geïntegreerd met de bestaande infrastructuur van Active Directory en databaseservers, zoals servers met Microsoft SQL Server™ 2000. Vanwege de kritische aard van deze ondersteunende onderdelen moet u RMS grondig testen in een geïsoleerde testomgeving voordat u RMS in de organisatie implementeert. Hierbij moet u afzonderlijke Active Directory- en databaseserver-installaties instellen in de testomgeving.

Begin met de meest eenvoudige configuratie van een RMS-server in een forest met een databaseserver en een client. Als u eenmaal weet hoe RMS werkt, kunt u de configuratie aanpassen aan de topologie die u wilt implementeren in de productieomgeving van uw organisatie, en zo nodig meerdere forest en externe toegang toevoegen. Hoewel in de testomgeving mogelijk niet alle configuraties voor de redundantie en de verschillende sites van het implementatieplan voor uw organisatie aanwezig zijn, moet deze minstens één server bevatten van elk ondersteunend onderdeel dat u wilt implementeren.

Hieronder wordt de minimale configuratie voor een testomgeving beschreven die u kunt gebruiken om een basisconfiguratie te testen voor RMS:

-   Een domeincontroller met Windows 2000 Server met Service Pack 3 (SP3) of hoger, en SQL Server 2000 met SP3a geïnstalleerd. SQL Server treedt op als host voor de logboekdatabase, configuratiedatabase en database met adreslijstservices van RMS. RMS kan met Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) versie A of SQL Server worden gebruikt als de database op dezelfde server wordt geïnstalleerd als RMS. Als u voor databaseondersteuning een externe server wilt gebruiken, is SQL Server vereist. U kunt MSDE 2000 vanaf de website van Microsoft downloaden.

| ![](images/Cc747673.note(WS.10).gif)Opmerking                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Windows 2000 Server met Service Pack 3 (SP3) is minimaal vereist voor de domeincontroller, maar Windows Server 2003 wordt aanbevolen vanwege de verbeterde prestaties in de Active Directory-groepsuitbreiding. Het wordt aangeraden MSDE 2000 alleen in testomgevingen te gebruiken ter ondersteuning van RMS-databases omdat MSDE 2000 geen ondersteuning biedt voor netwerkinterfaces. Bovendien bepalen de voorwaarden voor het gebruik van MSDE 2000 dat u geen SQL Server-clienthulpprogramma's mag gebruiken om een MSDE 2000 te bewerken. Door deze beperking kunt u geen logboekgegevens weergeven of opgeslagen gegevens in de configuratiedatabase wijzigen. |

-   Een basiscertificeringsserver met Windows Server 2003 waarop RMS is geïnstalleerd en ingericht. Als het voor het testen nodig mocht zijn, kunt u een basiscertificeringscluster maken door meer servers toe te voegen.
-   Een clientcomputer met Windows XP Professional, een RMS-client en een toepassing met RMS-ondersteuning.
-   Gebruikersaccounts met een e-mailadres in Active Directory.

Zie '[Een basisinfrastructuur instellen](https://technet.microsoft.com/3a0a3a47-e755-4455-bb22-0e05053723e4)' verder op in dit onderwerp voor meer informatie over de installatie en configuratie van een basisinfrastructuur met RMS en de toepassing van de infrastructuurvereisten in een productieomgeving.
