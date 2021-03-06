---
TOCTitle: 'Stap 5: clientupdates configureren'
Title: 'Stap 5: clientupdates configureren'
ms:assetid: '5ae60ead-3e94-456c-a692-c0f193ea5d5a'
ms:contentKeyID: 21798391
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Dd939830(v=WS.10)'
---

Stap 5: clientupdates configureren
==================================

Het installatieprogramma van WSUS configureert IIS automatisch om de meest recente versie van Automatische updates te installeren op elke clientcomputer die verbinding maakt met de WSUS-server.

Wat de beste manier is om Automatische updates te configureren, hangt af van uw netwerkomgeving. In een Active Directory®-omgeving kunt u gebruikmaken van een bestaand op domeinen gebaseerd groepsbeleidobject of u maakt een nieuw groepsbeleidobject. In een omgeving zonder Active Directory kunt u het lokale groepsbeleidsobject gebruiken. Tijdens deze stap configureert u Automatische updates en vervolgens verwijst u de clientcomputers naar de WSUS-server.

Bij de volgende procedures wordt aangenomen dat op uw netwerk Active Directory wordt uitgevoerd. Ook wordt aangenomen dat u weet hoe u met groepsbeleid moet werken en dat u bekend bent met hoe u groepsbeleid moet gebruiken voor het beheer van uw netwerk.

Zie de website over groepsbeleid op [http://go.microsoft.com/fwlink/?LinkID=47375](http://go.microsoft.com/fwlink/?linkid=47375) voor meer informatie over groepsbeleid.

 
-

Procedures voor stap 5
----------------------

Tijdens stap 4 hebt u het configureren voltooid van de updates die u wilt downloaden. U kunt deze reeks procedures gebruiken als u automatische updates voor clientcomputers wilt configureren.

1.  Automatische updates configureren via Groepsbeleid.
2.  De clientcomputer naar de WSUS-server verwijzen.
3.  Detectie door de WSUS-server handmatig starten.

U voert de eerste twee procedures uit op een groepsbeleidobject in een domein van uw keuze en de derde procedure via een opdrachtprompt op de clientcomputer.

**Automatische updates configureren**
1.  Blader in GPMC (Group Policy Management Console) naar het groepsbeleidobject waarvoor u WSUS wilt configureren en klik vervolgens op **Bewerken**.

2.  Vouw in GPMC achtereenvolgens **Computerconfiguratie**, **Beheersjablonen** en **Windows-onderdelen** uit en klik vervolgens op **Windows Update**.

3.  Dubbelklik in het detailvenster op **Automatische updates configureren**.

4.  Klik op **Ingeschakeld** en klik vervolgens op een van de volgende opties:

    -   **Downloaden en installeren melden**. Als u deze optie selecteert, krijgt een lid van de groep Administrators dat zich heeft aangemeld, een melding voordat de updates worden gedownload of geïnstalleerd.
    -   **Automatisch downloaden en melden voor het installeren**. Als u deze optie selecteert, worden de updates automatisch gedownload en krijgt vervolgens een lid van de groep Administrators dat zich heeft aangemeld, een melding voordat de updates worden geïnstalleerd.
    -   **Automatisch downloaden en de installatie plannen**. Als u deze optie selecteert, wordt het downloaden van updates automatisch gestart en de updates worden vervolgens geïnstalleerd op de dag die en het tijdstip dat u hebt opgegeven.
    -   **Lokale administrators kunnen de instelling kiezen**. Als u deze optie selecteert, kunnen lokale beheerders het onderdeel Automatische updates in het Configuratiescherm gebruiken om configuratieoptie te selecteren. Ze kunnen bijvoorbeeld voor de terugkerende geplande installatie een tijdstip kiezen dat hun het beste uitkomt. Lokale beheerders kunnen Automatische updates niet uitschakelen.

5.  Klik op **OK**.

**De clientcomputer naar de WSUS-server verwijzen**
1.  Dubbelklik in het detailvenster van **Windows Update** op **Locatie van Microsoft-updateservice in intranet**.

2.  Klik op **Ingeschakeld** en typ zowel in het vak **Stel de updateservice in het intranet in voor het detecteren van updates** als in het vak **Intranetserver voor statistische gegevens** de HTTP-URL van dezelfde WSUS-server. Typ bijvoorbeeld *http://servernaam* in beide vakken en klik op **OK**.

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" ><img src="images/Dd939830.note(WS.10).gif" />Opmerking</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Als u het lokale groepsbeleidsobject gebruikt om deze computer naar de WSUS-server te verwijzen, wordt deze instelling onmiddellijk van kracht en wordt deze computer na korte tijd in de WSUS-beheerconsole weergegeven. U kunt dit proces nog versnellen door handmatig een detectiecyclus te starten.
</td>
</tr>
</tbody>
</table>
 

Nadat u een clientcomputer hebt geconfigureerd, duurt het enkele minuten voordat deze computer op de pagina **Computers** in de WSUS-console wordt weergegeven. Voor clientcomputers die zijn geconfigureerd met een groepsbeleidsobject in een domein, is dat ongeveer 20 minuten nadat het groepsbeleid is vernieuwd (dat wil zeggen, nadat de nieuwe beleidsinstellingen op de clientcomputer zijn geconfigureerd). Het groepsbeleid wordt standaard elke 90 minuten (met een marge van 0 tot 30 minuten) op de achtergrond vernieuwd. Als u het groepsbeleid eerder wilt vernieuwen, geeft u op de clientcomputer de opdrachtprompt weer en typt u de volgende tekst: **gpupdate /force**.

Bij clientcomputers die zijn geconfigureerd met het lokale groepsbeleidsobject, wordt groepsbeleid onmiddellijk toegepast en duurt het vernieuwen ongeveer 20 minuten.

Als u het detecteren handmatig start, hoeft u niet 20 minuten te wachten voordat de clientcomputer verbinding maakt met de WSUS-server.

**Detectie door de WSUS-server handmatig starten**
1.  Klik op de clientcomputer op **Start** en klik op **Uitvoeren**.

2.  Typ **cmd** in het vak **Openen** en klik vervolgens op **OK**.

3.  Typ **wuauclt.exe /detectnow** achter de opdrachtprompt. Met deze opdrachtregeloptie geeft u Automatische updates de opdracht onmiddellijk verbinding te maken met de WSUS-server.

Volgende stap
-------------

[Stap 6: computergroepen configureren](https://technet.microsoft.com/70518732-2179-4e41-9609-7f9999867f41).

Aanvullende bronnen
-------------------

[Stapsgewijze handleiding voor Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)
