---
TOCTitle: 'RMS: Beheer'
Title: 'RMS: Beheer'
ms:assetid: '43f77336-5e62-4405-9efb-55417a402d62'
ms:contentKeyID: 18113963
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747547(v=WS.10)'
---

RMS: Beheer
===========

Beheren van RMS
---------------

-   [Wat is de beste manier om de machtigingen voor documenten in te trekken van een gebruiker die de organisatie gaat verlaten?](#bkmk_1)
-   [Moet er bij het instellen van een vertrouwensrelatie tussen twee organisaties voor het uitwisselen van RMS-inhoud iets speciaals worden gedaan voor het XrML-licentiecertificaat dat aan het vertrouwde bedrijf wordt doorgegeven?](#bkmk_2)
-   [Hoe werkt RMS bij zwervende gebruikersprofielen?](#bkmk_3)
-   [Waarom zou een organisatie RMS uit bedrijf willen nemen?](#bkmk_4)
-   [Wat is het algemene proces voor het uit bedrijf nemen?](#bkmk_5)
-   [Kan een RMS-server uit bedrijf worden genomen, zodat alleen bepaalde gebruikers documenten kunnen herstellen?](#bkmk_6)
-   [Wat betekent 'Server heeft geen toegang tot de toepassingsmap'?](#bkmk_7)
-   [Kan ik tracering op de RMS-server gebruiken?](#bkmk_8)
-   [Wat is tijdsverschil en hoe ga ik daarmee om?](#bkmk_9)

<span id="BKMK_1"></span>
#### Wat is de beste manier om de machtigingen voor documenten in te trekken van een gebruiker die de organisatie gaat verlaten?

Over het algemeen kunt u het beste voor documenten een licentie verlenen aan gebruikersgroepen die zijn gedefinieerd in Active Directory, in plaats van aan afzonderlijke gebruikersaccounts. Deze aanpak geniet de voorkeur omdat wanneer een gebruiker de organisatie verlaat, u die persoon uit de Active Directory-groep verwijdert. De documenten die naar die groep worden gestuurd, kunnen vervolgens niet meer worden gelezen door die betreffende persoon. Maar hij of zij kan nog steeds documenten lezen waaraan gebruikslicenties zijn verleend, tenzij er voor de documenten is ingesteld dat de gebruiker een gebruikslicentie moet aanvragen wanneer hij of zij een document opent. Als dat niet zo is ingesteld, kan alleen worden voorkomen dat de gebruiker documenten opent waaraan een gebruikslicentie is toegewezen, door de licentie-opslag van de gebruiker van diens computer te verwijderen.

<span id="BKMK_2"></span>
#### Moet er bij het instellen van een vertrouwensrelatie tussen twee organisaties voor het uitwisselen van RMS-inhoud iets speciaals worden gedaan voor het XrML-licentiecertificaat dat aan het vertrouwde bedrijf wordt doorgegeven?

Bij het instellen van een vertrouwd gebruikersdomein of een vertrouwd uitgiftedomein kunt u een vertrouwensrelatie met de partnerorganisatie instellen zodat die kan deelnemen in uw rechtenbeheersysteem. Hiermee neemt u een berekend risico, omdat het vertrouwen in de andere organisatie geen gevaar mag opleveren voor uw gegevens. Vraag daarom aan de partnerorganisatie of die het licentieverleningscertificaat van hun RMS-server via een gecontroleerd kanaal, zoals S/MIME-e-mail, naar u wil toesturen zodat er niet met het serverlicentieverleningscertificaat kan worden geknoeid voordat u het naar uw RMS-server importeert.

<span id="BKMK_3"></span>
#### Hoe werkt RMS bij zwervende gebruikersprofielen?

Rechtenaccountcertificaten (RAC's) waarmee gebruikers worden geïdentificeerd, zijn specifiek voor de betreffende computer. Bij gebruik van zwervende profielen zal er een nieuw rechtenaccountcertificaat voor de gebruiker worden gemaakt op de computer waarop RMS voor de eerste keer wordt gebruikt.

<span id="BKMK_4"></span>
#### Waarom zou een organisatie RMS uit bedrijf willen nemen?

Bij het uit bedrijf nemen van RMS wordt de RMS-server uit de infrastructuur verwijderd en kunnen gebruikers met rechten beveiligde inhoud zonder beveiliging opslaan. Er zijn drie belangrijke redenen waarom bedrijven dat zouden doen:

-   Voor het vereenvoudigen van het architectuurontwerp, zoals het consolideren van servers in een cluster.
-   Voor het migreren van een beproefde testomgeving naar een productieomgeving.
-   Voor het samenvoegen van RMS-servers na bijvoorbeeld een bedrijfsfusie.

<span id="BKMK_5"></span>
#### Wat is het algemene proces voor het uit bedrijf nemen?

Het uit bedrijf nemen wordt vanaf de RMS-basiscluster gestart door de service Uit bedrijf nemen te activeren. Wanneer deze service wordt ingeschakeld, worden alle andere services zoals licentieverlening en certificering uitgeschakeld. Vervolgens moet elke toepassing met RMS-ondersteuning van de gebruiker worden omgeleid om verbinding te kunnen maken met de service Uit bedrijf nemen wanneer er een RMS-functie wordt gebruikt. Microsoft Office 2003 is een voorbeeld van een toepassing met RMS-ondersteuning. In Office 2003 wordt de RMS-client met behulp van registersleutels omgeleid naar de RMS-services. De service Uit bedrijf nemen wordt door één sleutel in het register aangegeven. Als deze sleutel is ingesteld om de client om te leiden naar de service Uit bedrijf nemen, worden op de RMS-cluster licenties met alle machtigingen (lezen, schrijven, kopiëren, afdrukken, bewerken, enzovoort) aan de gebruiker voor die inhoud verleend, ongeacht of die machtigingen al eerder aan die gebruiker waren toegekend. Vervolgens moeten de gebruikers worden omgeleid om alle rechten van de beveiliging te verwijderen van elk document dat zij willen behouden nadat de RMS-cluster volledig uit bedrijf is genomen. Is deze procedure eenmaal voltooid, dan kan de RMS-cluster volledig uit bedrijf worden genomen.

Maak echter eerst een back-up van de configuratiedatabase van de RMS-cluster voor het geval u na het uit gebruik nemen van de cluster een met rechten beveiligd document moet herstellen. Zonder de persoonlijke sleutel van de RMS-basiscluster kan alleen de auteur van het document de met rechten beveiligde inhoud openen nadat de cluster is verwijderd.

<span id="BKMK_6"></span>
#### Kan een RMS-server uit bedrijf worden genomen, zodat alleen bepaalde gebruikers documenten kunnen herstellen?

U kunt een toegangscontrolelijst (ACL) op de webservice Uit bedrijf nemen (decommission.asmx) toepassen en de toegang tot deze service bepalen, zodat alleen bepaalde gebruikers de coderingssleutel voor de met rechten beveiligde inhoud kunnen ontvangen.

<span id="BKMK_7"></span>
#### Wat betekent 'Server heeft geen toegang tot de toepassingsmap'?

Deze fout wordt soms weergegeven wanneer u na het installeren van RMS de beheerwebsite van RMS probeert te openen. Als deze fout zich voordoet, kunt u RMS niet configureren of beheren.

Deze fout doet zich doorgaans voor wanneer IIS (Internet Information Services) in de IIS 5.0-isolatiemodus wordt uitgevoerd. U lost dit probleem op door als volgt deze instelling uit te schakelen en IIS opnieuw op te starten.

**De IIS 5.0-isolatiemodus uitschakelen**
1.  Meld u aan bij de RMS-server als lid van de groep lokale Administrators.

2.  Klik op **Start**, wijs **Systeembeheer** aan en klik vervolgens op **Beheer van Internet Information Services (IIS)**.

3.  Vouw in **IIS-beheer** de lokale computer uit, klik met de rechtermuisknop op **Websites** en klik op **Eigenschappen**.

4.  Klik op de tab **Service**, schakel het selectievakje **De WWW-service in IIS 5.0-isolatiemodus uitvoeren** uit en klik op **OK**.

5.  Hierdoor wordt de IIS-service opnieuw opgestart. Klik op **Ja** als wordt gevraagd of de IIS-service opnieuw moet worden opgestart.

<span id="BKMK_8"></span>
#### Kan ik tracering op de RMS-server gebruiken?

Omdat Rights Management Services is gemaakt met Microsoft® .NET Framework, kunt u door tracering in te schakelen systeemgebeurtenissen traceren en problemen oplossen.

U kunt tracering toepassen als u het bestand Web.config of Machine.config aanpast. Wanneer u tracering toepast op het bestand Machine.config, wordt tracering uitgevoerd op alle softwareonderdelen op de computer. Als u tracering toepast op het bestand Web.config, worden alleen gebeurtenissen getraceerd die plaatsvinden in de webservices.

**Tracering inschakelen**
1.  Open het bestand Machine.config of Web.config en voeg onder het gedeelte &lt;system.diagnostics&gt; de volgende regels toe aan het bestand:

    
        ```
2.  Typ IISRESET achter de opdrachtprompt om IIS opnieuw te starten.

3.  Nadat u de benodigde gegevens hebt verzameld, verwijdert u de regels die u in stap 1 hebt toegevoegd uit het CONFIG-bestand.

4.  Typ IISRESET achter de opdrachtprompt om IIS opnieuw te starten.

| ![](images/Cc747547.Important(WS.10).gif)Belangrijk                                                                                                                                                                                                                                                           |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Als u tracering op een RMS-server gebruikt, kunnen er problemen met de prestaties optreden, zoals langere vertragingen bij het verkrijgen van gebruikslicenties en het uitgeven van rechtenaccountcertificaten. Gebruik tracering alleen in bepaalde omstandigheden om een diagnose van bestaande problemen te maken en deze op te lossen. |

<span id="BKMK_9"></span>
#### Wat is tijdsverschil en hoe ga ik daarmee om?

Tijdsverschil is het verschil tussen de kloktijd op twee computers. Dit is heel normaal, zoals de horloges van twee mensen in een kamer ook niet precies gelijk lopen. Tijdsverschil kan een problemen veroorzaken wanneer u een geldigheidsduur opgeeft in een licentie.

Elke geldigheidsduur in een licentie wordt ingesteld volgens de klok van de uitgever. Tijdsverschil kan op twee plaatsen in de publicatiecyclus en de gebruikerscyclus problemen veroorzaken:

-   Als een toepassing een gebruikslicentie probeert te verkrijgen met een uitgiftelicentie die een geldigheidsduur heeft die in het verleden eindigt of in de toekomst begint volgens de klok van de RMS-server. In dat geval mislukt de aanvraag. Dit probleem kan optreden voor een eindgebruiker wanneer deze een gebruikslicentie aanvraagt, of voor een toepassing die probeert van tevoren een licentie te verkrijgen voor een document (een gebruikslicentie verkrijgen ten behoeve van een gebruiker).
-   Als de geldigheidsduur van de licentie is verlopen (of nog niet is begonnen), kan de licentie niet worden gebruikt. In andere gevallen zijn de rechten die zijn verlopen (of nog niet geldig zijn), niet beschikbaar.

Als de klok van de computer van een uitgever 15 minuten achterloopt op de klok van de computer van een gebruiker en de uitgever een licentie maakt waarin staat aangegeven dat de inhoud binnen 15 minuten verloopt, ontvangt de gebruiker een gebruikslicentie die niet kan worden gebruikt. Dat komt omdat de rechten voor het bekijken van de inhoud die de gebruiker via deze gebruikslicentie zou moeten krijgen, reeds zijn verlopen.

Er is geen allesomvattende oplossing voor problemen met tijdsverschillen. U kunt dit probleem ondervangen door de begintijd van de geldigheidsduur eerder in te stellen dan de huidige tijd voor gebruikers met klokken die achterlopen op die van u. U kunt zo mogelijk de geldigheidsduur van de licentie ook verlengen als de klok van de gebruiker voorloopt op die van u. Houd rekening met tijdsverschillen, vooral wanneer u kortdurende licenties gaat maken.
