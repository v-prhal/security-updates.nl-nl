---
TOCTitle: Leesmij voor WSUS met Service Pack 1
Title: Leesmij voor WSUS met Service Pack 1
ms:assetid: '937ecfe9-e8e0-41ac-85f7-4b65956f3d1e'
ms:contentKeyID: 18126886
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc708486(v=WS.10)'
---

Leesmij voor WSUS met Service Pack 1
====================================

Dit document worden bekende problemen met Windows Server Update Services met Service Pack 1 (WSUS met SP1) behandeld. Direct na de informatie over WSUS met SP1 vindt u alle informatie uit vorige versies van de originele WSUS-leesmijbestanden, onder andere aanbevelingen en vereisten voor het installeren van WSUS. Ga naar het [Microsoft Downloadcentrum](http://go.microsoft.com/fwlink/?linkid=67516) om WSUS met SP1 te downloaden.

Nieuw in WSUS met SP1
---------------------

WSUS met SP1 is een versie voor de verbetering van de beveiliging, betrouwbaarheid, schaalbaarheid, compatibiliteit en prestaties van WSUS. Dit zijn de nieuwe functies en verbeteringen:

-   Ondersteuning van Windows Vista-clients: computers met Windows Vista kunnen worden bijgewerkt door WSUS met SP1 Server.
-   Ondersteuning van meer clienttalen: ondersteuning van alle Office- en Windows Vista-talen.
-   Nieuwe versie van WMSDE: het exemplaar van WMSDE wordt door WSUS met SP1bijgewerkt tot WMSDE SP4 (WSUS RTM gebruikt WMSDE SP3).
-   Prestatieverbeteringen: WSUS met SP1 bevat diverse prestatieverbeteringen om de responstijden van gebruikersinterfaces te verbeteren.
-   Alle hotfixes: WSUS met SP1 bevat alle wijzigingen en hotfixes die na WSUS RTM zijn uitgebracht.
-   Ondersteuning van SQL Server 2005.

Voordat u begint met de upgrade naar WSUS met SP1
-------------------------------------------------

De volgende problemen zijn specifiek voor de upgrade naar WSUS met SP1. Onthoud dat de problemen en vereisten in het gedeelte "Voordat u begint" van de originele versie van dit onderwerp, niet in dit gedeelte voorkomen maar nog steeds van toepassing zijn. Zo zijn de installatievereisten in het originele gedeelte "Voordat u begint" nog steeds van toepassing.

**Opmerking**   Nadat u SP1 hebt toegepast op WSUS 2.0, kunt u de installatie van het servicepack niet ongedaan maken. Als u de installatie van SP1 ongedaan maakt, maakt u de installatie van het volledige product ongedaan.

**Belangrijk**   Dit document bevat informatie over het wijzigen van het register. Maak een back-up van het register voordat u wijzigingen aanbrengt. Zorg dat u weet hoe u een register kunt herstellen in het geval van problemen. Lees het volgende artikel in de Microsoft Knowledge Base voor meer informatie over back-ups maken van het register, het register herstellen en het register wijzigen.

[Beschrijving van het Microsoft Windows-register](http://support.microsoft.com/kb/256986) (http://support.microsoft.com/kb/256986/)

#### Probleem 1: Zorg dat u genoeg schijfruimte hebt voor een back-up van de database

Wanneer u een upgrade uitvoert van WSUS RTM, wordt tijdens de installatie van WSUS met SP1 automatisch een back-up van de WSUS-database gemaakt. Zorg dat er op het bestandssysteem van de WSUS-server genoeg schijfruimte is voor de back-up van de WSUS-database, anders mislukt de installatie van WSUS met SP1.

**Controleer als volgt of er genoeg schijfruimte is:**
1.  Open Windows Explorer en ga naar de map waarin de WSUS-database is opgeslagen. Standaard wordt de database opgeslagen in:

    
        ```
2.  Druk op **CTRL** en houd deze toets ingedrukt, selecteer **SUSDB.MDF** en **SUSDB\_log.LDF**. Klik met de rechtermuisknop en selecteer **Eigenschappen**.

3.  In het dialoogvenster **Bestanden** ziet u de waarde in **Grootte op schijf**. De schijf moet ten minste zo veel vrije schijfruimte hebben voor de installatie van WSUS met SP1.

4.  Klik in het menu **Start** op **Deze computer**. Controleer of de schijf waarop WSUS is geïnstalleerd de benodigde vrije schijfruimte heeft.

Als de installatie van WSUS met SP1 om wat voor reden dan ook mislukt, moet u handmatig de back-updatabase herstellen. Lees de [WSUS Operations Guide](http://technet2.microsoft.com/windowsserver/en/library/05f2e884-ae62-4c90-9681-6c9f2f3c9fd91033.mspx) voor instructies voor het herstellen van de WSUS-database.

#### Probleem 2: WSUS met SP1 kan alleen een upgrade van WSUS RTM uitvoeren

U kunt WSUS met SP1 alleen gebruiken om een upgrade van WSUS RTM uit te voeren. Momenteel is er nog geen ondersteuning voor een upgrade van de WSUS-releasekandidaat. Als u de WSUS-releasekandidaat of andere oudere versies van WSUS hebt geïnstalleerd, moet u de installatie van deze versies ongedaan maken en daarna WSUS met SP1 uitvoeren.

#### Probleem 3: De IIS-service van uw server wordt gestopt tijdens de upgrade naar WSUS met SP1

Het installatieprogramma van de upgrade naar WSUS met SP1 stopt de IIS-service (Internet Information Services) van uw server tijdens de upgrade. Dit betekent dat alle websites van de IIS-installatie op uw server niet beschikbaar zijn tijdens de upgrade. IIS wordt automatisch gestart na het voltooien van de upgrade.

#### Probleem 4: Tijdens de upgrade mag u geen toepassingen uitvoeren die WSUS API's aanroepen

Het aanroepen van WSUS API's (Application Programming Interfaces) veroorzaakt conflicten met de installatie van WSUS met SP1, waardoor de upgrade mislukt (u ontvangt een bericht waarin u wordt gevraagd de computer opnieuw op te starten om de upgrade te voltooien).

#### Probleem 5: Tijdens het uitvoeren van een upgrade naar WSUS met SP1 moet u mogelijk antivirusprogramma's uitschakelen

Wanneer u een upgrade van WSUS uitvoert met WSUS met SP1, moet u mogelijk antivirusprogramma's uitschakelen voordat u de upgrade kunt uitvoeren of u het servicepack kunt toepassen. Nadat u de antivirusprogramma's hebt uitgeschakeld, moet u de Windows Server-computer opnieuw opstarten voordat u de upgrade of het servicepack kunt toepassen. Door deze procedure zijn bestanden voor het upgradeproces niet geblokkeerd. Schakel uw antivirusprogramma weer in nadat de installatie is voltooid. Ga naar de website van de leverancier van uw antivirusprogramma voor de exacte stappen die u moet volgen om uw antivirusprogramma en -versie in en uit te schakelen.

| ![](images/Cc708486.Caution(WS.10).gif)Waarschuwing                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Deze oplossing kan uw computer of netwerk kwetsbaar maken voor aanvallen van kwaadwillende gebruikers of software zoals virussen. Wij raden u deze oplossing niet aan, maar geven u deze informatie zodat u deze oplossing naar eigen goeddunken kunt toepassen. Het gebruik van deze oplossing is op eigen risico. |

| ![](images/Cc708486.note(WS.10).gif)Opmerking                                                                                                                                                                                         |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Een antivirusprogramma is ontwikkeld om uw computer te helpen beschermen tegen virussen. Download en open geen bestanden van onbetrouwbare bronnen, bezoek geen onbetrouwbare websites en open geen e-mailbijlagen zolang het antivirusprogramma is uitgeschakeld. |

#### Probleem 6: Als u een proxyserver gebruikt, kan de upgrade naar SP1 de gebruikersnaam en het wachtwoord van de proxyconfiguratie wissen

Als u een proxyserver gebruikt, kan de upgrade naar SP1 in bepaalde gevallen de gebruikersnaam en het wachtwoord van de proxyconfiguratie wissen. Hierdoor kan de synchronisatie van updates van Microsoft Servers leiden tot de fout "ongeldige parameter". U kunt dit probleem oplossen door de gebruikersnaam en het wachtwoord van de proxyconfiguratie opnieuw in te stellen en uw server opnieuw te synchroniseren.

#### Probleem 7: Na een mislukte upgrade uw WSUS-server in een consistente status herstellen en de upgrade nogmaals proberen

Als de upgrade naar WSUS met SP1 mislukt, kan uw WSUS-installatie inconsistent of onbruikbaar zijn. Als u nogmaals wilt proberen een upgrade naar WSUS met SP1 uit te voeren, moet uw WSUS-installatie in een consistente status zijn. U kunt de installatie consistent maken door de back-updatabase die u hebt gemaakt aan het begin van het upgradeproces te gebruiken om uw WSUS-server te herstellen naar de status vóór de upgrade.

Volg na een mislukte upgrade deze stappen om nogmaals te proberen een upgrade naar WSUS met SP1 uit te voeren:

**Nogmaals proberen een upgrade naar WSUS met SP1 uit te voeren**
1.  Bepaal de locatie van de back-updatabase door de inhoud van het bestand WSUSSetup\_%timestamp%.log te bekijken. Dit bestand staat in de volgende map:

    -   %programfiles%\\Update Services\\LogFiles

2.  Zet de back-updatabase op de WSUS-computer terug met de volgende informatie:

    -   osql.exe -S &lt;DatabaseInstance&gt; -E -Q "USE master ALTER DATABASE SUSDB SET SINGLE\_USER WITH ROLLBACK IMMEDIATE RESTORE DATABASE SUSDB FROM DISK=N'&lt;PathToDatabaseBackup&gt;' WITH REPLACE ALTER DATABASE SUSDB SET MULTI\_USER"
    -   Vervang &lt;DatabaseInstance&gt; en &lt;PathToDatabaseBackup&gt; met de waarden van uw installatie.
    -   Gebruik voor &lt;DatabaseInstance&gt; de waarde van de volgende registersleutel:
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\SqlServerName
    -   Gebruik voor &lt;PathToDatabaseBackup&gt; de waarden die u hebt gevonden in stap 1.

3.  Verwijder WSUS maar behoud de WSUS-database, -logbestanden en -updatebestanden wanneer u wordt gevraagd deze te verwijderen. (Zorg dat alle opties in **Microsoft Windows Server Update Services verwijderen** zijn uitgeschakeld.)

4.  Installeer WSUS RTM (de originele versie, niet WSUS met SP1) opnieuw. Gebruik de bestaande database wanneer u hierom wordt gevraagd. Hierdoor krijgt uw WSUS-systeem weer een consistente status.

5.  Installeer WSUS met SP1.

**Opmerking**    U kunt de back-updatabase van stap 1 hiervoor niet direct gebruiken in een nieuwe installatie van WSUS met SP1. Het databaseschema is gewijzigd; deze database is niet compatibel zonder upgrade naar WSUS met SP1.

#### Probleem 8: De upgrade naar WSUS met SP1 kan in bepaalde gevallen mislukken wanneer de WMSDE-database is gemigreerd

De juiste oplossing is afhankelijk van het feit of u de database naar een lokale of externe SQL-server hebt gemigreerd.

#### WMSDE-database gemigreerd naar een lokale SQL 2000-server

Er moet een registersleutelwaarde worden gewijzigd zodat het installatiepakket voor WSUS met SP1 kan herkennen dat er geen WMSDE-database is die moet worden bijgewerkt.

Als u WMSDE hebt gemigreerd naar een lokale SQL 2000-server, moet u de volgende registerwijziging doorvoeren voordat u probeert een upgrade naar WSUS met SP1 uit te voeren:

-   Wijzig de waarde van de volgende registersleutel van "1" in "0":
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled  

#### WMSDE-database gemigreerd naar een externe SQL 2000-server

Er moet twee registersleutelwaarden worden gewijzigd zodat het installatiepakket voor WSUS met SP1 kan herkennen dat er geen WMSDE-database is die moet worden bijgewerkt. Eerst moet de back-end server worden bijgewerkt, daarna de front-end server.  

Als u WMSDE hebt gemigreerd naar een externe SQL 2000-server, moet u de volgende registerwijzigingen doorvoeren voordat u probeert een upgrade naar WSUS met SP1 uit te voeren:

1.  Wijzig de waarde van de volgende registersleutel van "1" in "0":
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled 
2.  Wijzig de waarde van de volgende registersleutel van "0x80" in "0x20":
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\InstallType 

Nadat u deze registersleutelwaarden hebt bijgewerkt, moet u de upgrade eerst op de back-end servers uitvoeren, en daarna op de front-end servers.

#### Probleem 9: WSUS met SP1 werkt WSUS-servers met externe SQL-installaties niet bij

U moet de installatie van WSUS met SP1 uitvoeren op zowel de front-end servers als de back-end servers.

**Een upgrade naar WSUS met SP1 uitvoeren bij gebruik van een externe SQL**
1.  Voer de installatie uit op de front-end zonder switches en kies voor een upgrade.

2.  Voer de installatie uit op de back-end zonder switches en kies voor een upgrade.

#### Probleem 10: Het wijzigen van de computernaam voorafgaand aan een upgrade naar WSUS met SP1 kan ertoe leiden dat de upgrade mislukt

Als u de computernaam wijzigt ná de installatie van WSUS RTM en vóór de upgrade naar WSUS met SP1, kan de upgrade mislukken.

Gebruik het volgende script om de groepen Administrators ASPNET en WSUS te verwijderen en opnieuw toe te voegen. Voer de upgrade daarna opnieuw uit.

        ```
| ![](images/Cc708486.note(WS.10).gif)Opmerking                                         |
|--------------------------------------------------------------------------------------------------------------------|
| Mogelijk moet u &lt;ContentDirectory&gt; in de laatste regel vervangen door het pad naar uw huidige inhoudsopslag. |

Originele inhoud van WSUS-leesmij
---------------------------------

Hierna vindt u de originele inhoud van de WSUS-leesmij. De volgende problemen komen *niet* voor in WSUS met SP1. Deze informatie staat hier slechts voor uw gemak.

Voordat u begint
----------------

#### Probleem 1: IIS moet zijn geïnstalleerd

Microsoft® Windows Server™ Update Services (WSUS) vereist dat Internet Information Services (IIS) is geïnstalleerd. Onder Microsoft Windows Server 2003 en Microsoft Windows® 2000 Server wordt IIS echter niet standaard geïnstalleerd. Daarom kan Setup van Windows Server Update Services mogelijk niet verdergaan. In dat geval wordt er een foutbericht weergegeven met de melding dat IIS niet is geïnstalleerd.

Ga als volgt te werk om IIS te installeren:

1.  Open het Configuratiescherm.
2.  Dubbelklik op **Software**.
3.  Klik op **Windows-onderdelen toevoegen of verwijderen**.
4.  Klik in de lijst **Onderdelen** op **Toepassingsserver**.
5.  Klik op **Details**.
6.  Schakel het selectievakje **ASP.NET** in. Schakel **COM+ netwerktoegang** in. IIS (Internet Information Services ) wordt nu automatisch geselecteerd.
7.  Selecteer **Internet Information Services (IIS)** en klik op **Details** om de lijst met optionele IIS-onderdelen weer te geven.
8.  Selecteer alle optionele onderdelen die u wilt installeren. Het optionele onderdeel World Wide Web Service bevat belangrijke subonderdelen, zoals Active Server Pages en Extern beheer (HTML). Klik op World Wide Web-service en vervolgens op Details als u deze subonderdelen wilt weergeven en selecteren. Klik op OK totdat u bent teruggekeerd bij de wizard Windows-onderdelen.
9.  Klik op **Volgende** en voltooi de wizard Windows-onderdelen.
10. Nadat u IIS hebt geïnstalleerd, kunt u Setup van Windows Server Update Services uitvoeren.

#### Probleem 2: Voor servers waarop Windows 2000 Server wordt uitgevoerd, dient ten minste één website in IIS aanwezig te zijn voordat u WSUS installeert

Mogelijk maakt het installatieprogramma van Windows Server Update Services geen website als er in IIS geen websites aanwezig zijn op het moment dat Setup wordt uitgevoerd. Dit kan bijvoorbeeld het geval zijn als een SUS 1.0-website (Software Update Services) de enige website in IIS was en u deze website hebt verwijderd voordat u WSUS installeerde.

In dat geval dient u een nieuwe website te maken met de module Beheer van Internet Information Services. Als u eenmaal een website hebt gemaakt, kunt u deze website selecteren of een nieuwe website opgeven tijdens de installatie van WSUS.

Als u al hebt geprobeerd om WSUS te installeren en de installatie is mislukt omdat er geen websites aanwezig waren, opent u de module Beheer van Internet Information Services en verwijdert u de site 'Website nr.1'. Voer vervolgens de hiervoor beschreven stappen uit en voer Setup opnieuw uit.

#### Probleem 3: Noodzakelijke onderdelen installeren

#### Softwarevereisten

In de volgende tabel wordt de vereiste software voor elk ondersteund besturingssysteem weergegeven. Zorg ervoor dat de WSUS-server voldoet aan de vereisten in deze lijst voordat u Setup van WSUS uitvoert. Als een van deze updates vereist dat de computer opnieuw wordt gestart wanneer de installatie is voltooid, dient u de server opnieuw te starten voordat u WSUS installeert.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Besturingssysteem</th>
<th style="border:1px solid black;" >Vereisten</th>
<th style="border:1px solid black;" >Downloads</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Alle besturingssystemen</td>
<td style="border:1px solid black;">Microsoft Internet Information Services (IIS) 5.0</td>
<td style="border:1px solid black;">Moet worden geïnstalleerd vanuit het besturingssysteem.
Zie probleem 1: IIS moet zijn geïnstalleerd.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Alle besturingssystemen</td>
<td style="border:1px solid black;">Intelligente achtergrondsoverdrachtservice 2.0</td>
<td style="border:1px solid black;">Voor besturingssystemen met Windows Server 2003, zie Update voor Intelligente achtergrondsoverdrachtservice 2.0 en WinHTTP 5.1 Windows Server 2003 (KB842773) in het Download Center (<a href="http://go.microsoft.com/fwlink/?linkid=47251">http://go.microsoft.com/fwlink/?LinkId=47251</a>).
Voor besturingssystemen met Windows Server 2000, zie Update voor Intelligente achtergrondsoverdrachtservice 2.0 en WinHTTP 5.1 Windows 2000 (KB842773) in het Download Center (<a href="http://go.microsoft.com/fwlink/?linkid=46794">http://go.microsoft.com/fwlink/?LinkId=46794</a>).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003</td>
<td style="border:1px solid black;">Microsoft .NET Framework 1.1 Service Pack 1 voor Windows Server 2003</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47358">Microsoft .NET Framework 1.1 Service Pack 1 voor Windows Server 2003</a>
U kunt ook naar <a href="http://go.microsoft.com/fwlink/?linkid=47370">Windows Update</a> gaan, zoeken naar essentiële updates en servicepacks, en Microsoft .NET Framework 1.1 Service Pack 1 voor Windows Server 2003 installeren.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server 2003</td>
<td style="border:1px solid black;">Databasesoftware die volledig compatibel is met Microsoft SQL</td>
<td style="border:1px solid black;">N.v.t.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Databasesoftware die volledig compatibel is met Microsoft SQL</td>
<td style="border:1px solid black;">Als u Microsoft SQL Server 2000 niet gebruikt, kunt u Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) installeren. Hiertoe moet u enkele stappen uitvoeren. Zie het gedeelte 'MSDE onder Windows 2000 installeren', dat hierna wordt weergegeven, voor meer informatie.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Microsoft Internet Explorer 6.0 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47359">Internet Explorer 6 Service Pack 1</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Herdistribueerbaar pakket voor Microsoft .NET Framework Versie 1.1</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47369">Herdistribueerbaar pakket voor Microsoft .NET Framework Versie 1.1</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Microsoft .NET Framework 1.1 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47368">Microsoft .NET Framework 1.1 Service Pack 1</a>
U kunt ook naar de website <a href="http://go.microsoft.com/fwlink/?linkid=47370">Windows Update</a> gaan, zoeken naar essentiële updates en servicepacks, en Microsoft .NET Framework 1.1 Service Pack 1 voor Windows Server 2000 installeren.</td>
</tr>
</tbody>
</table>
 

Behalve deze vereiste software zal WSUS mogelijk ook ASP.NET versie 1.1 op de server installeren of configureren, als dat nodig is. (Setup van WSUS configureert ASP.NET.)

#### MSDE 2000 onder Windows 2000 installeren

Als u Windows 2000 voor WSUS gebruikt en u geen toegang hebt tot Microsoft SQL Server 2000, dient u Microsoft SQL Server 2000 Desktop Engine (MSDE) te installeren voordat u Setup van WSUS uitvoert. Als MSDE al is geïnstalleerd op uw WSUS-server, hoeft u geen speciale versie van MSDE voor WSUS te installeren. U kunt eenvoudig de naam van de bestaande instantie opgeven tijdens de installatie van WSUS.

Het installeren van MSDE onder Windows 2000 Server is een procedure die uit vier stappen bestaat. Eerst moet u het MSDE-archief downloaden en uitpakken in een map op de WSUS-server. Vervolgens moet u de opdrachtprompt en opdrachtregelopties gebruiken om Setup van MSDE uit te voeren, het wachtwoord van de systeembeheerder in te stellen en WSUS als de naam van de instantie toe te wijzen. Als de installatie van WSDE is voltooid, moet u controleren of de WSUS-instantie wordt uitgevoerd als een NT-service. Tot slot moet u een beveiligingspatch aan MSDE toevoegen om de WSUS-server te beveiligen.

#### Stap 1: MSDE-archief downloaden en uitpakken

Het MSDE-archief downloaden en uitpakken in een map op uw WSUS-server. Zie [Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) Release A](http://go.microsoft.com/fwlink/?linkid=47366).

#### Stap 2: MSDE installeren

Gebruik de opdrachtprompt en opdrachtregelopties om Setup van MSDE uit te voeren, het wachtwoord voor de systeembeheerder in te stellen en WSUS als de naam van de instantie toe te wijzen. Als de installatie van WSDE is voltooid, moet u controleren of de WSUS-instantie wordt uitgevoerd als een NT-service.

MSDE installeren, het wachtwoord van de systeembeheerder instellen en een instantienaam toewijzen:

1.  Ga bij de opdrachtprompt naar de installatiemap voor MSDE die u hebt opgegeven bij "Stap 1: Het MSDE-archief downloaden en uitpakken".
2.  Typ het volgende: **setup sapwd="***wachtwoord***" instancename=WSUS**
    waarbij *wachtwoord* een sterk wachtwoord is voor de account van de systeembeheerder van deze instantie van MSDE, en **instancename** de naam is van de database-instantie. U kunt ook de standaardinstantienaam (in plaats van 'WSUS') gebruiken voor de WSUS-database. Als u voor deze mogelijkheid kiest, hoeft u niet **instancename=WSUS** te typen op de opdrachtregelparameter. Met deze opdracht start u het installatieprogramma van MSDE, stelt u het wachtwoord van de systeembeheerder in en geeft u deze instantie van MSDE de door u gewenste naam.

#### Stap 3: Controleren of de WSUS-instantie van MSDE is geïnstalleerd

1.  Klik op **Start** en vervolgens op **Uitvoeren**.
2.  Typ **services.msc** in het dialoogvenster **Openen** en klik op **OK**.

Schuif omlaag in de lijst met services en controleer of er een service met de naam MSSQL$WSUS (als 'WSUS' is gebruikt als instantienaam) of MSSQLSERVER (als de standaardinstantienaam is gebruikt) aanwezig is.

#### Stap 4: De MSDE-instantie starten

Aan het eind van de MSDE-installatie moet u de instantie starten. Als "WSUS" is gebruikt als instantienaam, start u "MSSQL$WSUS". Als de standaardinstantienaam is gebruikt, start u MSSQLSERVER. WSUS kan de database-instantie alleen gebruiken als deze service is gestart.

#### Stap 5: MSDE bijwerken

U moet de beveiligingspatch in [MS03-031: Cumulatieve beveiligingspatch voor SQL Server](http://go.microsoft.com/fwlink/?linkid=47364) downloaden en installeren.

Ga naar [SQL Server 2000 (32-bit) Beveiligingspatch MS03-031](http://go.microsoft.com/fwlink/?linkid=47363) om de beveiligingspatch te downloaden.

#### Probleem 4: Minimale eisen die worden gesteld aan de schijfruimte

Hier volgen de minimale eisen die worden gesteld aan de schijfruimte voor het installeren van Windows Server Update Services:

-   1 GB (gigabyte) op de systeempartitie
-   2 GB voor het volume waarop de databasebestanden worden opgeslagen
-   6 GB, gebaseerd op de verwachte aantallen gegevens

#### Probleem 5: Eerdere versies van WSUS moeten worden verwijderd met het onderdeel Software in het Configuratiescherm voordat u de meeste recente versie installeert

Als u van plan bent Windows Server Update Services te installeren op een server waarop Windows Update Services Beta 1 of Beta 2 is geïnstalleerd, moet u eerst de eerdere versie verwijderen via het onderdeel Software in het Configuratiescherm.

#### Probleem 6: WSUS vereist dat de optie voor geneste triggers in SQL Server is ingeschakeld

Deze optie is standaard ingeschakeld, maar kan worden uitgeschakeld door een SQL Server-beheerder.

Als u van plan bent een SQL Server-database als gegevensarchief voor Windows Server Update Services te gebruiken, moet de SQL Server-beheerder controleren of de optie voor geneste triggers is ingeschakeld voordat de WSUS-beheerder WSUS installeert en de database opgeeft tijdens de installatie.

Setup van WSUS schakelt de optie RECURSIVE\_TRIGGERS in, wat een database-specifieke optie is. Setup schakelt de optie voor geneste triggers echter niet in omdat dat een algemene optie is die geldt voor de hele server.

Als u wilt controleren of de optie voor geneste triggers is ingeschakeld, gebruikt u de volgende opdracht:

**sp\_configure 'nested triggers'**

Als u de optie voor geneste triggers in SQL Server wilt inschakelen, voert u de volgende opdracht uit vanuit een batchbestand op de computer waarop SQL Server wordt uitgevoerd:

**sp\_configure 'nested triggers', 1**

**GO**

**RECONFIGURE**

**GO**

#### Probleem 7: Opdrachtregelparameters voor Setup van WSUS

U kunt WSUS laten installeren zonder toezicht te hoeven houden. Zie voor meer informatie en opdrachtregelparameters "Appendix A: Unattended Installation" in [Deploying Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=41777) (Engels).

Bekende problemen
-----------------

#### Probleem 1: Wizard IIS-beveiliging

Als u IIS (Internet Information Services) uitvoert op een computer met Windows 2000 Server, dient u de meest recente versie van de wizard IIS-beveiliging (die URLScan bevat) te installeren vanaf de pagina IIS Lockdown Tool op Microsoft TechNet. Microsoft raadt u met klem aan dit hulpprogramma te installeren om ervoor te zorgen dat de IIS-servers goed beveiligd zijn. De wizard IIS-beveiliging schakelt functies van IIS die kunnen leiden tot beveiligingsproblemen, uit. Daarmee worden de beveiligingsrisico's verkleind.

| ![](images/Cc708486.note(WS.10).gif)Opmerking                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Setup van WSUS installeert deze onderdelen niet. U dient deze onderdelen handmatig te installeren. U hoeft de IIS-beveiliging niet te installeren op computers waarop Windows Server 2003 wordt uitgevoerd, omdat deze functionaliteit in dit besturingssysteem is ingebouwd. |

#### Probleem 2: U kunt de WSUS-configuratie niet rechtstreeks in de database wijzigen

De configuratiegegevens van Windows Server Update Services worden in een database opgeslagen (in MSDE of SQL Server). U kunt de configuratiegegevens echter niet wijzigen door rechtstreeks in de database wijzigingen aan te brengen. Beheerders mogen niet proberen de WSUS-configuratie op deze manier te wijzigen. U kunt de WSUS-configuratie wel wijzigen via de WSUS-console of door WSUS-API's aan te roepen.

#### Probleem 3: U kunt alleen toegang krijgen tot de WSUS-beheersite als het actief uitvoeren van scripts is ingeschakeld

U moet op het werkstation van de beheerder Internet Explorer zodanig configureren dat dit programma het actief uitvoeren van scripts toestaat voordat u Internet Explorer kunt gebruiken om toegang te krijgen tot de WSUS-beheersite.

#### Probleem 4: IIS wordt opnieuw opgestart tijdens de installatie van WSUS

Tijdens de installatie van Windows Server Update Services wordt IIS zonder voorafgaand bericht opnieuw opgestart. Dit kan invloed hebben op bestaande websites binnen uw onderneming.

#### Probleem 5: De toegangsmachtigingen voor de virtuele map voor WSUS of SMS-beheerpunten wijzigen

Voor de virtuele map voor Windows Server Update Services is standaard anonieme toegang toegestaan. Als u deze instelling wijzigt en verificatie vereist, kunnen clients als gevolg van verificatiefouten geen toegang meer krijgen tot deze map en dus geen updates downloaden.. Dit is een bekend probleem: Winhttp.dll gebruikt de verkeerde verificatiecontext wanneer impliciete verificatie is vereist, waardoor de verificatie mislukt. U kunt voorkomen dat dit probleem zich voordoet door ervoor te zorgen dat de WSUS-server en de SMS-beheerpunten anoniem toegang kunnen krijgen tot de virtuele mappen van IIS.

#### Probleem 6: Als u WSUS onder Windows Small Business Server 2003 installeert, moeten de toegangsinstellingen voor de virtuele WSUS-hoofdmap van de standaardwebsite worden gewijzigd om WSUS-clients in staat te stellen zichzelf bij te werken vanaf de server

De WSUS-server installeert de twee virtuele hoofdmappen SelfUpdate en ClientWebService, en enkele bestanden in de basismap van de standaardwebsite (op poort 80). Hierdoor kunnen clients zichzelf bijwerken via de standaardwebsite. In Windows Small Business Server 2003 is de standaardwebsite echter standaard zodanig geconfigureerd dat deze elk IP-adres of elke localhost de toegang weigert, behalve het IP-adres of de localhost van de server. Dit betekent dat clients de toegang tot de virtuele hoofdmappen SelfUpdate en ClientWebService wordt geweigerd en dat de clients zichzelf dus niet kunnen bijwerken. Als u clients toegang wilt verlenen tot de standaardwebsite, zodat ze zichzelf kunnen bijwerken, brengt u de volgende wijzigingen aan in de virtuele hoofdmappen SelfUpdate en ClientWebService van de website.

1.  Klik in de virtuele hoofdmap op **Eigenschappen**, klik op **Mapbeveiliging**, klik op **IP-adres en domeinnaambeperkingen** en klik op **Bewerken**.
2.  Selecteer **Toegang verleend** en klik op **OK**. Sluit alle eigenschappenvensters

#### Probleem 7: Integratieproblemen bij het installeren van WSUS onder Small Business Server

-   Als Windows Small Business Server 2003 een ISA-proxyserver gebruikt om toegang te krijgen tot internet, moeten de volgende instellingen handmatig bij **Instellingen** worden ingevoerd: de instellingen, naam en poort van de proxyserver.
-   Als ISA Windows-verificatie gebruikt, moeten de proxyserver-referenties in de volgende vorm worden ingevoerd: "DOMEIN\\gebruiker" (de gebruiker die behoort tot de groep Internetgebruikers).

#### Probleem 8: Als een computer van de ene naar de andere computergroep wordt verplaatst, kan het maximaal één uur duren voordat op de beheerconsole de computer in de nieuwe groep wordt weergegeven

Als een computer voor de eerste keer aan een doelgroep wordt toegewezen, worden de gegevens op de computer bijgewerkt met de gegevens over de groep. Deze gegevens worden periodiek of elk uur vernieuwd. Als een computer van de ene naar de andere computergroep wordt verplaatst, kan het daarom maximaal één uur duren voordat de gegevens op de client worden vernieuwd en de gewijzigde gegevens op de WSUS-beheerconsole worden weergegeven.

#### Probleem 9: Als u WSUS op een lidserver installeert en u de lidserver vervolgens wilt promoveren tot een domeincontroller, dient u WSUS eerst weer van de server te verwijderen

Als u WSUS op een lidserver installeert en u de lidserver vervolgens wilt promoveren tot een domeincontroller, dient u de volgende stappen uit te voeren:

1.  Verwijder WSUS.
2.  Promoveer de lidserver tot domeincontroller.
3.  Installeer WSUS opnieuw.

#### Probleem 10: Als u een WSUS-server wilt degraderen van een domeincontroller tot een lidserver, dient u eerst WSUS te verwijderen

Als u WSUS uitvoert op een domeincontroller en u de domeincontroller wilt degraderen tot een lidserver, dient u de volgende stappen uit te voeren:

1.  Verwijder WSUS, maar behoud de database.
2.  Maak een gebruikersaccount met de naam ASPNET.
3.  Typ **aspnet\_regiis -i** achter de opdrachtprompt.
4.  Installeer WSUS opnieuw en gebruik de behouden database.

#### Probleem 11: Als .NET Framework 1.0 of 2.0 wordt geïnstalleerd nadat WSUS is geïnstalleerd, wordt de WSUS-beheerconsole niet weergegeven

Dit probleem wordt veroorzaakt door het feit dat .NET Framework 1.0 is geregistreerd bij IIS terwijl WSUS Server .NET Framework 1.1 nodig heeft. U kunt dit probleem oplossen door aspnet\_regiis.exe te openen en de volgende opdrachten uit te voeren, waarbij *website id* de waarde is in de volgende registersleutel:

HKLM\\Software\\Microsoft\\WindowsUpdateServices\\Server\\Setup\\IISTargetWebsiteIndex

-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\ReportingWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\ClientWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\SimpleAuthWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\WSUSAdmin
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\AdministrationWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\ServrSyncWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\DssAuthWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*website id*&gt;\\ROOT\\Content

#### Probleem 12: Beperkingen voor externe SQL

WSUS biedt slechts beperkte ondersteuning voor het uitvoeren van databasesoftware op een computer die gescheiden is van de computer met de rest van de WSUS-toepassing.

-   U kunt Windows 2000 Server niet gebruiken als de front-end computer in een computerpaar dat externe SQL gebruikt.
-   U kunt geen server die is geconfigureerd als een domeincontroller, als front-end of back-end computer gebruiken in een computerpaar dat externe SQL gebruikt.
-   U kunt geen gebruikmaken van WMSDE of MSDE voor databasesoftware op de back-end computer.
-   Een externe SQL-server (te gebruiken als de WSUS-database) instellen mislukt als Terminal Services is geïnstalleerd op de externe server en in de toepassingsmodus wordt uitgevoerd. Wanneer u SQL Server installeert op een Terminal Services-server, moet u het volgende doen:
    1.  Voordat u de installatie uitvoert, opent u een opdrachtprompt en typt u: "change user /install"
    2.  Voer de installatie van SQL Server uit.
    3.  Na de installatie, typt u in de opdrachtprompt: "change user /execute"
-   U moet lid zijn van de beveiligingsgroep lokale beheerders op zowel de front-end als de back-end computer om de externe SQL Server WSUS-database te kunnen installeren.
-   Meer informatie over problemen met externe SQL, vindt u in "Appendix C: Remote SQL" in [Deploying Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=41777) (Engels).

#### Probleem 13: Een downstream-server in replicamodus heeft mogelijk minder goedkeuringen dan de bovenliggende upstream-server

Een downstream-server in replicamodus heeft mogelijk minder goedkeuringen dan de bovenliggende upstream-server. De reden hiervoor is dat installatiegoedkeuringen niet naar een downstream-server gaan tot alle gegevens naar de upstream-server zijn geladen.

#### Probleem 14: Synchronisatie opnieuw proberen na mislukte synchronisatie

Als de synchronisatie mislukt, moet u eerst proberen de server opnieuw te synchroniseren. Als de synchronisatie daarna nog steeds niet lukt, moet u de informatie voor probleemoplossing in de WSUS Operations Guide raadplegen.

#### Probleem 15: Als u probeert de beheerconsole voor WSUS te openen, wordt het foutbericht System.IO.FileNotFoundException weergegeven

Als het onderstaande foutbericht wordt weergegeven, moet u mogelijk machtigingen wijzigen op de Network Service- of ASP.NET-accounts:

System.IO.FileNotFoundException: Kan de bestands- of assembly-naam *xxxxxx*.dll, of een afhankelijkheid ervan, niet vinden

Hierbij is *xxxx* een willekeurige naam.

U kunt dit probleem in besturingssystemen met Windows Server 20003 oplossen door de Network Service-account een machtiging voor lezen en schrijven toe te kennen voor %systemroot%\\Temp. In Windows 2000 Server kent u de ASP.NET-account een machtiging voor lezen en schrijven toe voor %systemroot%\\Temp.

#### Probleem 16: Beveiligingsupdate voor SQL MS03-031 (KB815495)

Deze update kan mogelijk als geïnstalleerd worden aangegeven op de WSUS-server, ook al is de installatie op de client in werkelijkheid mislukt. Hierdoor wordt het pakket mogelijk opnieuw aan de client aangeboden. U kunt dit probleem verhelpen door de goedkeuring voor de update op de server in te trekken.

#### Probleem 17: IIS-instellingen gaan verloren tijdens RTM-upgrade

Als u WSUS RTM installeert op een server met een eerdere versie van WSUS (bijvoorbeeld RC), wordt door WSUS RTM de oude versie verwijderd en de nieuwe versie geïnstalleerd. Dit houdt in dat de virtuele hoofdmappen en bestanden voor WSUS in IIS worden verwijderd.

Als u WSUS hebt geïnstalleerd op de standaardwebsite, gaan alle instellingen voor WSUS die u in de virtuele hoofdmappen van WSUS hebt aangebracht, verloren. Als u de virtuele hoofdmappen bijvoorbeeld hebt geconfigureerd voor SSL om WUS te beveiligen, moet u deze opnieuw configureren nadat u de RTM-versie van WSUS hebt geïnstalleerd. Opmerking: er wordt een waarschuwing weergegeven op de WSUS-console dat SSL niet is ingeschakeld.

Als u WSUS had geïnstalleerd op een andere website dan de standaardwebsite, gaan alle aanvullende instellingen op websiteniveau voor WSUS verloren.

#### Probleem 18: Hostkopteksten gebruiken

Als u waarden voor hostkopteksten wilt toewijzen aan de standaardwebsite (WSUS-website) in IIS, moet u 'Alle niet-toegewezen' of een toegewezen IP-adres toevoegen aan de lijst met IP-adressen zonder waarde voor hostkoptekst voor de standaardwebsite. Dit moet ook worden toegevoegd voor andere websites dan de standaardwebsite.

**Waarschuwing**: hierdoor kan de functionaliteit van Microsoft SharePoint en Exchange worden beëindigd.

#### Probleem 19: De URL van de WSUS-console moet worden toegevoegd aan de lijst met vertrouwde websites en lokale intranetzones op computers waarvoor beveiligingsopties voor Internet Explorer zijn ingeschakeld

Als u beveiligingsopties voor Internet Explorer (ook wel het onderdeel Microsoft Windows Server 2003 Internet Explorer Enhanced Security Configuration genoemd) op een computer hebt ingeschakeld en de WSUS-console niet toevoegt aan de lijst met vertrouwde websites en lokale intranetzones, wordt telkens als u een pagina in de WSUS-console opent naar gebruikersreferenties gevraagd.

Ga als volgt te werk om de WSUS-console toe te voegen aan de zones **Lokaal intranet** en **Vertrouwde websites**:

1.  Open **Internet-opties** (klik bijvoorbeeld op **Start**, wijs **Configuratiescherm** aan klik op **Internet-opties**).
2.  Ga naar het tabblad **Beveiliging**, klik op **Lokaal intranet**, klik op **Websites**, klik op **Geavanceerd**, voeg de URL toe (http://*WSUSServername*/WSUSAdmin) en klik op **OK**.
3.  Klik op **Vertrouwde websites**, klik op **Websites**, voeg de URL van de WSUS-console toe en klik op **OK**. Klik nogmaals op **OK** om **Internet-opties** te verlaten.

#### Copyright

De informatie in dit document weerspiegelt de huidige zienswijze van Microsoft Corporation over de onderwerpen die vanaf de publicatiedatum zijn besproken. Aangezien Microsoft moet reageren op een veranderende marktsituatie, vormt dit document geen garantie van de zijde van Microsoft en kan Microsoft de juistheid van deze informatie die na de publicatiedatum wordt gepresenteerd, niet garanderen.

Dit document is alleen bedoeld ter informatie. MICROSOFT BIEDT GEEN GARANTIES MET BETREKKING TOT DE INFORMATIE IN DIT DOCUMENT, ONGEACHT OF DEZE GARANTIES EXPLICIET, IMPLICIET OF WETTELIJK ZIJN.

Het is de verantwoordelijkheid van de gebruiker zich te houden aan alle relevante copyrightwetgeving. Met inachtneming van de geldende auteursrechten, mag niets uit dit document worden gereproduceerd, opgeslagen in of toegevoegd aan gegevensbestanden, of openbaar gemaakt in enige vorm of op enige wijze, hetzij elektronisch, mechanisch, door opnamen of anderszins, of voor andere doeleinden worden gebruikt, zonder schriftelijke toestemming van Microsoft Corporation.

Microsoft heeft mogelijk patenten, patentaanvragen, merken, auteursrechten of andere intellectuele eigendomsrechten die van toepassing zijn op de inhoud in dit document. Tenzij uitdrukkelijk anders vermeld in de schriftelijke gebruiksrechtovereenkomst van Microsoft, geeft dit document u geen recht op deze patenten, merken, auteursrechten of andere intellectuele eigendommen.

Tenzij anders vermeld, zijn alle in dit document vermelde bedrijven, organisaties, producten, domeinnamen, e-mailadressen, logo's, personen, plaatsen en gebeurtenissen fictief. Eventuele overeenkomsten met bestaande bedrijven, organisaties, producten, domeinnamen, e-mailadressen, logo's, personen, plaatsen en gebeurtenissen berusten geheel op toeval.

© 2006 Microsoft Corporation. Alle rechten voorbehouden.

Microsoft, SQL Server, Windows en Windows Server zijn merken of gedeponeerde merken van Microsoft Corporation.

De namen van bestaande bedrijven en producten die in dit document worden vermeld, kunnen merken zijn van de desbetreffende eigenaren.
