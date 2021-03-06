---
TOCTitle: 'Plannen voor externe RMS-gebruikers'
Title: 'Plannen voor externe RMS-gebruikers'
ms:assetid: '107e1338-4dcf-4ed5-a49d-e875cc883db1'
ms:contentKeyID: 18113841
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720190(v=WS.10)'
---

Plannen voor externe RMS-gebruikers
===================================

In dit gedeelte leest u hoe u een topologie implementeert waarmee uw organisatie en externe gebruikers door RMS beveiligde inhoud kunnen delen via internet.

U kunt met een van de volgende opties RMS-clusters voor zowel intern als extern gebruik implementeren:

-   Stel de URL van het basiscertificeringscluster in op een URL die via internet kan worden benaderd. Zorg dat deze URL binnen het intranet wordt herleid naar RMS-servers voor hetzelfde cluster. Wanneer u dit doet, werkt de URL voor de uitgiftelicentie die door de computers van de eindgebruikers wordt gebruikt voor het aanvragen van licenties, zowel binnen het intranet als op internet.
-   Stel een afzonderlijk RMS-cluster speciaal voor publiceren op internet in. Alle inhoud waarvoor een licentie vanaf internet moet worden verstrekt, moet naar dit cluster worden gepubliceerd. Als inhoud zowel intern als extern beschikbaar moet zijn, moet die op beide locaties worden gepubliceerd. Een andere mogelijkheid is de gebruikers in staat te stellen contact te maken met de internetserver.

Externe gebruikers toestaan
---------------------------

U kunt externe gebruikers in uw RMS-installatie opnemen als u interne accounts voor die gebruikers maakt en de gebruikers toegang biedt tot uw bedrijfsnetwerk middels een VPN (virtueel particulier netwerk). De account kan een interne postbus of een e-mailadres hebben dat naar een externe postbus verwijst.

Als u een interne postbus gebruikt, moeten interne auteurs wanneer zij door RMS beveiligde inhoud publiceren, het e-mailadres opgeven dat is gekoppeld aan die interne postbus (in plaats van het e-mailadres dat de externe gebruiker heeft buiten uw organisatie). Als u een externe postbus gebruikt, moeten interne auteurs het externe e-mailadres van de account opgeven wanneer zij door RMS beveiligde inhoud publiceren.

Wanneer u netwerkbeveiliging in stand wilt houden terwijl u toch toegang tot uw netwerk door externe gebruikers wilt ondersteunen, kunt u een afzonderlijk Active Directory-forest maken voor partneraccounts. Met deze topologie kunt u een afzonderlijke basiscertificeringscluster maken voor het internetgerichte gedeelte van het RMS-systeem. Op die manier kunnen externe gebruikers het computercertificaat en accountcertificaat van RMS van dit internetgerichte basiscertificeringscluster ophalen wanneer deze gebruikers voor de eerste keer toegang krijgen tot door RMS beveiligde inhoud.

Wanneer u voor externe partners een afzonderlijk forest met de partneraccounts wilt implementeren, moet RMS in dat forest worden geïnstalleerd. Vervolgens kunt u met de RMS-functie voor vertrouwde uitgiftedomeinen een vertrouwensrelatie tussen de twee RMS-servers instellen. De externe DNS records moeten de externe cluster-URL identificeren van de RMS-installatie in het forest dat voor de externe partners is gemaakt. Door deze vertrouwensrelatie te maken kan de externe RMS-server gebruikslicenties uitgeven voor alle inhoud die door het interne RMS-systeem wordt uitgegeven en vice versa.

In plaats van een RMS-server in het externe forest te installeren kunt u ook met bijvoorbeeld een ISA-server inkomend gegevensverkeer filteren en licentie-aanvragen van de RMS-proxy naar de interne RMS-server sturen.

Externe certificaten gebruiken
------------------------------

U kunt externe gebruikers toegang bieden tot door RMS beveiligde inhoud als u een RMS-server instelt als een internetgerichte licentieserver, de inhoud vanaf die licentieserver publiceert en vervolgens vertrouwensrelaties op die server specificeert.

Het internetgerichte gedeelte van de RMS-installatie is een afzonderlijke licentieserver die exclusief is bestemd voor gebruik op internet. Deze server is een onderdeel van hetzelfde cluster als de interne licentieverleningsinstallatie en maakt gebruik van dezelfde database en dezelfde URL als de interne licentieverleningsinstallatie. Het is de enige server die inkomend internetverkeer kan accepteren.

Wanneer externe gebruikers een gebruikslicentie bij deze RMS-licentieserver aanvragen, gebruiken zij een rechtenaccountcertificaat van een andere RMS-certificeringsservice die deze licentieserver moet vertrouwen.

#### Op Passport gebaseerde rechtenaccountcertificaten als vertrouwd aanmerken

U kunt voor uw organisatie de keuze maken rechtenaccountcertificaten te vertrouwen die zijn gebaseerd op Microsoft .NET Passport-referenties. Bij deze accountcertificaten moeten de gebruikers rechtenaccountcertificaten rechtstreeks ophalen van de Microsoft Certification Service die op internet wordt gehost.

In dit model ontvangen externe gebruikers RMS-computercertificaten en RMS-accountcertificaten van Microsoft. Wanneer de inhoud wordt gepubliceerd, moet de Microsoft .NET Passport-account van de externe gebruiker als ontvanger worden genoemd in de uitgiftelicentie.

De Microsoft .NET Passport-account moet overeenkomen met de .NET Passport-account die is gebruikt toen het RMS-accountcertificaat werd gedownload van Microsoft. De auteur moet die account opgeven bij het toevoegen van ontvangers aan de toepassing met RMS-ondersteuning. Als de accounts niet overeenkomen, kan de inhoud niet worden geconsumeerd.

#### Andere externe certificaten vertrouwen

Als het bedrijf van de externe gebruiker eveneens over een RMS-installatie beschikt, kunt u een vertrouwensrelatie met dat bedrijf realiseren. U vraagt het bedrijf dan het serverlicentiecertificaat van RMS te exporteren en naar u toe te sturen. U kunt het certificaat vervolgens importeren met de RMS-beheerconsole voor de internetgerichte licentieserver.
