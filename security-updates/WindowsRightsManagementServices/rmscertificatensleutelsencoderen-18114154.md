---
TOCTitle: 'RMS: Certificaten, sleutels en coderen'
Title: 'RMS: Certificaten, sleutels en coderen'
ms:assetid: 'ad8cc088-1dea-44c2-be68-9091129f0f12'
ms:contentKeyID: 18114154
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747725(v=WS.10)'
---

RMS: Certificaten, sleutels en coderen
======================================

Certificaten, sleutels en codering in RMS
-----------------------------------------

-   [Welke coderingsalgoritmen worden gebruikt in RMS?](#bkmk_10)
-   [Wordt in RMS door FIPS gecertificeerde codering gebruikt?](#bkmk_11)
-   [Worden bij uitgiftelicenties of -sjablonen waarmee machtigingen aan een distributielijst in plaats van aan individuele gebruikers worden toegewezen, gebruikslicenties anders afgehandeld om de leden dynamisch te kunnen evalueren?](#bkmk_12)
-   [Wanneer RMS vanuit een kiosk wordt gebruikt, wordt er een tijdelijk rechtenaccountcertificaat uitgegeven. Op welke manier verschilt een tijdelijk rechtenaccountcertificaat van een standaardrechtenaccountcertificaat? Hoe 'weet' RMS dat het in een kiosk wordt gebruikt?](#bkmk_13)
-   [Wanneer wordt er een tijdelijk rechtenaccountcertificaat gebruikt?](#bkmk_14)
-   [Worden er door RMS X.509v3-certificaten uitgegeven?](#bkmk_15)
-   [Waar worden XrML-certificaten opgeslagen?](#bkmk_16)
-   [Waar wordt het persoonlijke-sleutelpaar of het openbare-sleutelpaar van de computer opgeslagen?](#bkmk_17)
-   [Waar wordt het persoonlijke-sleutelpaar of het openbare-sleutelpaar van de client opgeslagen?](#bkmk_18)
-   [AES is een symmetrische algoritme. Hoe worden sleutels veilig uitgewisseld tussen de server en de gebruiker?](#bkmk_19)

<span id="BKMK_10"></span>
#### Welke coderingsalgoritmen worden gebruikt in RMS?

RMS gebruikt RSA-sleutels van 2048-bits voor de RMS-server en RSA-sleutels van 1024-bits voor het sleutelpaar van de gebruiker en de computer.

<span id="BKMK_11"></span>
#### Wordt in RMS door FIPS gecertificeerde codering gebruikt?

In RMS met Service Pack 1 en hoger gebruiken de lockboxes die door de RMS-clienttoepassing worden gegenereerd, door FIPS gecertificeerde AES-codering wanneer de client is geïnstalleerd op een computer met Windows XP of Windows Server 2003. Als de RMS-client echter wordt geïnstalleerd op computers met Windows 2000, wordt er geen door FIPS gecertificeerde AES-bibliotheek geïnstalleerd. De lockboxes zijn dan niet compatibel met FIPS.

<span id="BKMK_12"></span>
#### Worden bij uitgiftelicenties of -sjablonen waarmee machtigingen aan een distributielijst in plaats van aan individuele gebruikers worden toegewezen, gebruikslicenties anders afgehandeld om de leden dynamisch te kunnen evalueren?

Gebruikslicenties worden altijd uitgegeven aan individuele gebruikers. Als er in een uitgiftelicentie of -sjabloon een groep staat vermeld, wordt in RMS het lidmaatschap van de groep geëvalueerd op het moment dat de gebruikslicentie wordt uitgegeven. Als de aanvrager van de licentie lid is van die groep, wordt de gebruikslicentie verleend aan de identiteit van de gebruiker.

<span id="BKMK_13"></span>
#### Wanneer RMS vanuit een kiosk wordt gebruikt, wordt er een tijdelijk rechtenaccountcertificaat uitgegeven. Op welke manier verschilt een tijdelijk rechtenaccountcertificaat van een standaardrechtenaccountcertificaat? Hoe 'weet' RMS dat het in een kiosk wordt gebruikt?

Door de toepassing met RMS-ondersteuning moet worden bepaald of de RMS-client een tijdelijk of een standaardrechtenaccountcertificaat voor de gebruiker moet aanvragen. Er is geen enkele methode waarop deze situatie kan worden gedetecteerd. Microsoft Office 2003 is een voorbeeld van een toepassing met RMS-ondersteuning waarmee de gebruiker het juiste rechtenaccountcertificaat kan selecteren.

Het grote verschil tussen een tijdelijk rechtenaccountcertificaat en een standaardrechtenaccountcertificaat is de aanwezigheid van de beveiligings-id van de gebruiker en de opgegeven geldigheidsduur. De gebruikers-SID staat niet in tijdelijke rechtenaccountcertificaten en voor deze certificaten wordt de geldigheidsduur opgegeven in minuten. De standaardgeldigheidsduur voor een tijdelijk rechtenaccountcertificaat is 15 minuten. Standaardrechtenaccountcertificaten bevatten echter gebruikers-SID en voor deze certificaten wordt de geldigheidsduur opgegeven in dagen. De standaardgeldigheidsduur voor een standaardrechtenaccountcertificaat is 365 dagen.

<span id="BKMK_14"></span>
#### Wanneer wordt er een tijdelijk rechtenaccountcertificaat gebruikt?

Met een tijdelijk rechtenaccountcertificaat kan een gebruiker door RMS beveiligde inhoud verwerken op computers die aan de volgende criteria voldoen:

-   De computer is geen lid van hetzelfde forest als de RMS-installatie vanwaar het rechtenaccountcertificaat is ontvangen.
-   De computer is geen lid van hetzelfde forest waar de gebruikersaccount zich bevindt.
-   Het is niet zeker of de gebruiker steeds op dezelfde computer werkt.

Computers die aan deze criteria voldoen, zijn de computers op bijvoorbeeld vliegvelden, in openbare bibliotheken en in internetcafés.

<span id="BKMK_15"></span>
#### Worden er door RMS X.509v3-certificaten uitgegeven?

Nee. In RMS worden XrML-certificaten uitgegeven die zijn bedoeld voor het vertegenwoordigen van gebruikers en een beleid dat buiten het bereik van X.509v3-certificaten valt.

<span id="BKMK_16"></span>
#### Waar worden XrML-certificaten opgeslagen?

In een RMS-systeem worden de volgende certificaten en licenties gebruikt die in XrML op de clientcomputer zijn opgeslagen.

-   Computercertificaat
    Bestandsnaam: Bestand CERT-Machine.drm
    Locatie: %USERPROFILE%\\Local Settings\\Application Data\\Microsoft\\DRM\\
-   Rechtenaccountcertificaat
    Het voorvoegsel van de bestandsnaam: GIC
    Locatie: %USERPROFILE%\\Local Settings\\Application Data\\Microsoft\\DRM
-   Clientlicentieverleningscertificaat
    Het voorvoegsel van de bestandsnaam: CLC
    Locatie: %USERPROFILE%\\Local Settings\\Application Data\\Microsoft\\DRM
-   Gebruikslicentie
    Het voorvoegsel van de bestandsnaam: EUL
    Locatie: %USERPROFILE%\\Local Settings\\Application Data\\Microsoft\\DRM

| ![](images/Cc747725.note(WS.10).gif)Opmerking                                                                                |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Een gebruikersaccount heeft één computercertificaat, één GIC-bestand en één CLC-bestand, maar meerdere EUL-bestanden voor elke inhoud die wordt benaderd. |

| ![](images/Cc747725.note(WS.10).gif)Opmerking                                       |
|------------------------------------------------------------------------------------------------------------------|
| Voor de met Windows Vista® geïntegreerde RMS-client is de locatie %USERPROFILE%\\AppData\\Local\\Microsoft\\DRM. |

<span id="BKMK_17"></span>
#### Waar wordt het persoonlijke-sleutelpaar of het openbare-sleutelpaar van de computer opgeslagen?

De persoonlijke sleutel van de computer wordt veilig opgeslagen en wordt beveiligd door de cryptografiesleutels die horen bij de aanmeldingsreferenties van de gebruiker en de computerconfiguratie.

<span id="BKMK_18"></span>
#### Waar wordt het persoonlijke-sleutelpaar of het openbare-sleutelpaar van de client opgeslagen?

Het sleutelpaar voor een gebruikersaccount wordt opgeslagen in het rechtenaccountcertificaat.

<span id="BKMK_19"></span>
#### AES is een symmetrische algoritme. Hoe worden sleutels veilig uitgewisseld tussen de server en de gebruiker?

In het systeem worden zowel symmetrische als openbare of persoonlijke sleutels gebruikt. De inhoud wordt gecodeerd met een symmetrische sleutel. De andere sleutels in het systeem (voor de gebruikers, computers en servers) zijn de openbare en persoonlijke sleutels van RSA. De symmetrische inhoudssleutel is altijd gecodeerd in de diverse licenties voor de openbare sleutel van RSA voor de RMS-server in de uitgiftelicentie of voor de openbare sleutel van RSA voor de gebruiker in de gebruikslicentie.
