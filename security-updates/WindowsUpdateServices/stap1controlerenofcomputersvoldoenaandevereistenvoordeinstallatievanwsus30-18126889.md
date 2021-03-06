---
TOCTitle: 'Stap 1: controleren of computers voldoen aan de vereisten voor de installatie van WSUS 3.0'
Title: 'Stap 1: controleren of computers voldoen aan de vereisten voor de installatie van WSUS 3.0'
ms:assetid: '912b37d7-021e-4c95-b317-49dd15b4611c'
ms:contentKeyID: 18126889
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc708484(v=WS.10)'
---

Stap 1: controleren of computers voldoen aan de vereisten voor de installatie van WSUS 3.0
==========================================================================================

In deze handleiding wordt uitgelegd hoe u WSUS 3.0 installeert. Raadpleeg de release-opmerkingen ([http://go.microsoft.com/fwlink/?LinkId=71220](http://go.microsoft.com/fwlink/?linkid=71220)) voor Windows Server 2003 Service Pack 1 en Windows Server® 2008-besturingssystemen voor informatie over softwarevereisten en ondersteunde platforms voor WSUS 3.0.

Softwarevereisten voor het installeren van WSUS 3.0 onder Windows Server 2003 Service Pack 1
--------------------------------------------------------------------------------------------

Als u WSUS 3.0 wilt installeren onder Windows Server 2003 Service Pack 1, moet het volgende op uw computer zijn geïnstalleerd. Als een van deze updates vereist dat de server opnieuw wordt gestart wanneer de installatie is voltooid, dient u de server opnieuw te starten voordat u WSUS 3.0 installeert.

-   Microsoft Internet Information Services (IIS) 6.0.
-   Update voor Background Intelligent Transfer Service (BITS) 2.0 en WinHTTP 5.1 Windows Server 2003. Als u deze software wilt downloaden, gaat u naar het Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkID=47251](http://go.microsoft.com/fwlink/?linkid=47251)).
-   Herdistribueerbaar pakket voor Microsoft .NET Framework versie 2.0 (x86). Als u deze software wilt downloaden, gaat u naar het Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkID=68935](http://go.microsoft.com/fwlink/?linkid=68935)). (Voor 64-bits platforms gaat u eveneens naar het Downloadcentrum \[[http://go.microsoft.com/fwlink/?LinkID=70637](http://go.microsoft.com/fwlink/?linkid=70637)\].)
-   Microsoft Report Viewer Redistributable 2005. Als u deze software wilt ophalen, gaat u naar het Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkID=70410](http://go.microsoft.com/fwlink/?linkid=70410)).
-   Microsoft Management Console 3.0 voor Windows Server 2003 (KB907265). Als u deze software wilt downloaden, gaat u naar het Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkID=70412](http://go.microsoft.com/fwlink/?linkid=70412)). (Voor 64-bits platforms gaat u eveneens naar het Downloadcentrum \[[http://go.microsoft.com/fwlink/?LinkID=70638](http://go.microsoft.com/fwlink/?linkid=70638)\].)

Softwarevereisten voor het installeren van WSUS 3.0 onder Windows Server 2008
-----------------------------------------------------------------------------

Als u WSUS 3.0 wilt installeren onder Windows Server 2008, moet het volgende op de computer zijn geïnstalleerd. Als een van deze updates vereist dat de server opnieuw wordt gestart wanneer de installatie is voltooid, dient u de server opnieuw te starten voordat u WSUS 3.0 installeert.

-   Microsoft Internet Information Services (IIS) 7.0. Zorg ervoor dat de volgende onderdelen zijn ingeschakeld:
    -   Windows-verificatie
    -   ASP.NET
    -   6.0-beheercompatibiliteit
    -   IIS-metabasecompatibiliteit
-   Microsoft Report Viewer Redistributable 2005. Als u deze software wilt downloaden, gaat u naar het Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkID=70410](http://go.microsoft.com/fwlink/?linkid=70410)).
-   Microsoft SQL Server™ 2005 Service Pack 1. Als u deze software wilt downloaden, gaat u naar het Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkID=66143](http://go.microsoft.com/fwlink/?linkid=66143)).

De .NET Framework 2.0- en BITS 2.0-update zijn als onderdeel van het besturingssysteem beschikbaar bij Windows Server 2008.

Vereisten en aanbevelingen voor de vaste schijf
-----------------------------------------------

Als u WSUS 3.0 wilt installeren, moet het bestandssysteem van de server aan de volgende vereisten voldoen:

-   Zowel de systeempartitie als de partitie waarop u WSUS 3.0 installeert, moeten zijn geformatteerd met het NTFS-bestandssysteem.
-   Voor de systeempartitie wordt minimaal 1 GB vrije geheugenruimte aanbevolen.
-   Voor het volume waar WSUS-gegevens worden opgeslagen, is minimaal 20 GB vrije geheugenruimte vereist; 30 GB vrije geheugenruimte wordt aanbevolen.
-   Voor het volume waar het installatieprogramma van WSUS Windows® Internal Database installeert, wordt minimaal 2 GB vrije geheugenruimte aanbevolen.

Installatievereisten voor de console
------------------------------------

U kunt nu met WSUS 3.0 de WSUS-beheerconsole op externe systemen buiten de WSUS-server om installeren. Installaties van alleen de console kunnen worden uitgevoerd bij de volgende besturingssystemen:

-   Windows Server® 2008
-   Windows Vista®
-   Windows Server 2003 Service Pack 1
-   Windows XP Service Pack 2

Hieronder volgen de softwarevereisten voor de installatie van de console

-   Herdistribueerbaar pakket voor Microsoft .NET Framework versie 2.0 (x86), beschikbaar in het Microsoft Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkId=68935](http://go.microsoft.com/fwlink/?linkid=68935)). Voor 64-bits platforms gaat u naar Herdistribueerbaar pakket voor Microsoft .NET Framework versie 2.0 (x86) ([http://go.microsoft.com/fwlink/?LinkId=70637](http://go.microsoft.com/fwlink/?linkid=70637)).
-   Microsoft Management Console 3.0 voor Windows Server 2003 (KB907265), beschikbaar in het Microsoft Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkId=70412](http://go.microsoft.com/fwlink/?linkid=70412)). Voor 64-bits platforms gaat u naar Microsoft Management Console 3.0 voor Windows Server 2003 x64 Edition (KB907265) ([http://go.microsoft.com/fwlink/?LinkId=70638](http://go.microsoft.com/fwlink/?linkid=70638)).
-   Microsoft Report Viewer Redistributable 2005, beschikbaar in het Microsoft Downloadcentrum ([http://go.microsoft.com/fwlink/?LinkId=70410](http://go.microsoft.com/fwlink/?linkid=70410)).

Vereisten voor de service Automatische updates
----------------------------------------------

De service Automatische updates is het onderdeel van WSUS 3.0 voor clientcomputers. Automatische updates stelt geen speciale eisen aan de hardware, maar de computer dient wel verbinding te hebben met het netwerk. U kunt Automatische updates in combinatie met WSUS 3.0 gebruiken op computers met een van de volgende besturingssystemen:

-   Windows Vista.
-   Windows Server® 2008.
-   Microsoft Windows® Server 2003, alle versies en service packs.
-   Microsoft Windows XP Professional, Service Pack 1 of Service Pack 2.
-   Microsoft Windows 2000 Professional Service Pack 4, Windows 2000 Server Service Pack 4 of Windows 2000 Advanced Server Service Pack 4.

Machtigingen
------------

De volgende machtigingen voor toegang tot de vaste schijf moeten worden toegekend aan de opgegeven gebruikers voor de opgegeven mappen:

1.  Ofwel de geïntegreerde groep Gebruikers of de account NT Authority\\Netwerkservice (onder Windows Server 2003) moet leesmachtiging hebben voor de basismap op het station waarop zich de WSUS-inhoudsmap bevindt. Als deze machtiging ontbreekt, mislukken BITS-downloads.
2.  De account NT Authority\\Netwerkservice moet de machtiging 'Volledig beheer' hebben voor de WSUS-inhoudsmap, gewoonlijk &lt;SystemDriver&gt;:WSUS\\WsusContent. Deze machtiging wordt ingesteld door het installatieprogramma voor de WSUS-server op het moment dat de map wordt gemaakt, maar in sommige gevallen wordt deze machtiging gewijzigd door beveiligingssoftware. Als deze machtiging ontbreekt, mislukken BITS-downloads.
3.  De account NT Authority\\Netwerkservice moet de machtiging 'Volledig beheer' hebben voor de volgende mappen om de WSUS-beheermodule juist te kunnen weergeven:
    -   %windir%\\Microsoft .NET\\Framework\\v2.0.50727\\Temporary ASP.NET Files
    -   %windir%\\Temp

Raadpleeg het artikel waarin wordt beschreven waarom DCPROMO geen machtigingen in stand houdt voor sommige IIS-mappen ([http://go.microsoft.com/fwlink/?LinkID=76332](http://go.microsoft.com/fwlink/?linkid=76332)) voor meer informatie over het instellen van machtigingen.
