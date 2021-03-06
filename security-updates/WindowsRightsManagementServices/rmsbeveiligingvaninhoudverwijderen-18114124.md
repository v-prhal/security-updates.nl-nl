---
TOCTitle: 'RMS-beveiliging van inhoud verwijderen'
Title: 'RMS-beveiliging van inhoud verwijderen'
ms:assetid: 'c30361e3-50d2-4474-a87d-d38de502cf9e'
ms:contentKeyID: 18114124
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747658(v=WS.10)'
---

RMS-beveiliging van inhoud verwijderen
======================================

Bepaal van tevoren welke bestanden door wie en wanneer moeten worden hersteld, zodat er geen belangrijke gegevens verloren gaan wanneer het proces voor het uit bedrijf nemen wordt uitgevoerd. Wanneer de RMS-beveiliging van alle betrokken, door RMS beveiligde bestanden is verwijderd, kan de server uit de infrastructuur worden verwijderd.

RMS-beveiliging wordt als volgt van de inhoud verwijderd:

1.  De gebruiker moet alle gebruikslicenties van de computer verwijderen. Hierdoor haalt de RMS-client op de server een licentie voor het openen van de inhoud op. Gebruikslicenties worden opgeslagen in de map %GEBRUIKERSPROFIEL%\\Local Settings\\Application Data\\Microsoft\\DRM op de clientcomputer en hebben het voorvoegsel EUL bij de bestandsnaam.
2.  Een gebruiker met toegang tot de server voor het uit bedrijf nemen probeert een door RMS beveiligd bestand te openen.
3.  De toepassing maakt verbinding met de server voor het uit bedrijf nemen en ontvangt de sleutel voor de inhoud.
4.  De inhoud wordt gedecodeerd en kan worden bewerkt, opgeslagen, doorgestuurd en afgedrukt.
5.  De gebruiker slaat de inhoud zonder RMS-beveiliging op. Alle gebruikers kunnen nu de inhoud openen zonder dat zij daarvoor verbinding met de RMS-server moeten maken.
