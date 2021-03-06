---
TOCTitle: Problemen met het inrichten van RMS
Title: Problemen met het inrichten van RMS
ms:assetid: 'b0e6ef48-ab38-4426-be5b-811cf64c45c0'
ms:contentKeyID: 18114110
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747638(v=WS.10)'
---

Problemen met het inrichten van RMS
===================================

Wanneer u RMS inricht, worden de bronbestanden en verbindingen tussen de diverse onderdelen die in RMS worden gebruikt, geconfigureerd en ingesteld. Als er zich een fout voordoet tijdens het instellen van een bron, kan er niet worden ingericht en wordt er een foutbericht weergegeven. In dit gedeelte worden de meest voorkomende oorzaken van deze fouten besproken. Aan de hand hiervan kunt u de eventuele problemen oplossen, zodat u RMS verder kunt inrichten.

De basiscertificeringsserver kan niet worden ingericht
------------------------------------------------------

U kunt een basiscertificeringsserver waarschijnlijk niet inrichten, omdat de inrichtingspagina's niet worden weergegeven. Dit probleem kan optreden wanneer u op de optie RMS op deze website inrichten klikt om de eerste basiscertificeringsserver in te richten vanaf de pagina Algemeen beheer. In plaats van de pagina's voor het inrichten van de basiscertificeringsserver worden de pagina's voor het inrichten van een licentieserver weergegeven.

Dit probleem treedt op wanneer u een basiscertificeringsserver probeert in te richten en de inrichting van de laatste basiscertificeringsserver in dit Active Directory-forest niet ongedaan is gemaakt voordat u de installatie van RMS ongedaan maakt. Wanneer u de inrichting van de enige basiscertificeringsserver in een Active Directory-forest ongedaan maakt, verwijdert u het serviceverbindingspunt uit Active Directory. Als u de inrichting van de laatste basiscertificeringsserver in het forest niet ongedaan maakt voordat u de installatie van RMS ongedaan maakt, moet u het serviceverbindingspunt handmatig uit Active Directory verwijderen voordat u opnieuw een basiscertificeringsserver in dit forest kunt inrichten.

Als de inrichtingspagina's voor een licentieserver worden weergegeven bij het inrichten van de eerste basiscertificeringsserver in een Active Directory-forest, verwijdert u als volgt het serviceverbindingspunt uit Active Directory:

**Het serviceverbindingspunt uit RMS verwijderen**
1.  Installeer zo nodig de Windows Server-hulpprogramma's voor ondersteuning:

    Voer voor Windows Server 2003 het bestand Suptools.msi uit. Dit bestand bevindt zich in de map \\Support\\Tools op de installatie-cd-rom.

    Voer voor Windows 2000 Server het bestand Setup.exe uit. Dit bestand bevindt zich in de map \\Support Tools op de installatie-cd-rom.

2.  Meld u aan bij de domeincontroller van het domein waarvan de basiscertificeringsserver lid is, door een account te gebruiken die lid is van de groep Domeinadministrators.

3.  Typ de volgende opdrachtregel en druk op ENTER:

    **ldp**

4.  Klik op **Connection** en vervolgens op **Connect**.

5.  Druk op ENTER. Typ geen gegevens.

6.  Klik op **Connection** en vervolgens op **Bind**.

7.  Druk op ENTER. Typ geen gegevens.

8.  Klik op **View** en vervolgens op **Tree**.

9.  Druk op ENTER. Typ geen gegevens.

    **dc=YourDomain,dc=com** wordt weergegeven in het linkerdeelvenster.

10. Vouw **dc=YourDomain,dc=com** uit.

11. Vouw **Configuratie** uit

12. Vouw **Services** uit.

13. Verwijder **RightsManagementServices**.

- of -

1.  Download en installeer de Administration Toolkit voor RMS. U kunt de toolkit downloaden vanaf de [website van Microsoft](http://go.microsoft.com/fwlink/?linkid=33841).
2.  Open de opdrachtprompt door op **Start** en vervolgens op **Uitvoeren** te klikken. In het dialoogvenster **Uitvoeren** typ **cmd** en klik op **OK**.
3.  Typ de volgende opdrachtregel op de opdrachtprompt:
    **ADSCPRegister.exeunregisterscp** &lt;*URLtoUnRegister*&gt;
4.  Typ voor &lt;*URLtoUnRegister*&gt; de URL van het RMS-serviceverbindingspunt, bijvoorbeeld https://my\_domain/\_wmcs/Certification.

Nadat u deze stappen hebt voltooid, kunt u de basiscertificeringsserver inrichten.

Kan geen SSPI-context genereren
-------------------------------

Mogelijk ontvangt u tijdens het inrichten het foutbericht 'Kan geen SSPI-context genereren'. Dit gebeurt als de RMS-serviceaccount niet is geverifieerd wanneer de basiscertificeringsserver wordt ingeschreven bij de inschrijvingsservice van Microsoft.

Als u dit foutbericht ontvangt, controleert u of de RMS-serviceaccount een geldige domeinaccount is. Als de account een groepsaccount is, controleert u of het groepslidmaatschap geldig is, of u alle gebruikersaccounts in de groep in het domein kunt herleiden en of de accounts machtigingen hebben voor toegang tot de SQL-databases.
