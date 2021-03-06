---
TOCTitle: Beheerwebsite van RMS
Title: Beheerwebsite van RMS
ms:assetid: 'f003c1d9-9a17-4e50-9e1e-5d67677552a0'
ms:contentKeyID: 18114235
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747796(v=WS.10)'
---

Beheerwebsite van RMS
=====================

Alle basisclusters en clusters die alleen voor licentieverlening worden gebruikt, bieden een beheerwebsite waarmee u RMS kunt beheren. Deze website is alleen beschikbaar op de RMS-server die u beheert, of via een verbinding met een extern bureaublad.

In dit onderwerp wordt beschreven welke functies u kunt uitvoeren via de beheerwebsite. Zie 'Procedures voor RMS...' en 'RMS beheren' in 'Een RMS-server beheren' in de documentatie voor instructies voor het beheren van RMS met de website.

**Opmerking** Clusterconfiguraties worden algemeen toegepast. Op elke server in het cluster kunt u de configuratie voor een cluster beheren via de beheerwebsite.

Open de pagina **Algemeen beheer** en voer de volgende taken uit:

-   RMS inrichten op een website.
-   Een server inrichten en toevoegen aan een cluster.
-   RMS verwijderen van een website.
-   Naar de beheerpagina's voor het cluster gaan.

Open de pagina **Beheer** voor een cluster als u de volgende taken wilt uitvoeren:

-   **Clusterinformatie weergeven.**U kunt clustergegevens weergeven, zoals de installatie-URL, server-URL, certificaatnaam, configuratiedatabaseserver, configuratiedatabasenaam en verloopdatum van het certificaat.
-   **Het serverlicentieverleningscertificaat inschrijven of vernieuwen.**U kunt het serverlicentieverleningscertificaat voor het cluster inschrijven of vernieuwen.
-   **Vertrouwensbeleid instellen.** Klik op de koppeling om de webpagina Vertrouwensbeleid te openen. Hier kunt u vertrouwde gebruikers- en uitgiftedomeinen toevoegen en verwijderen. Voeg gebruikers toe aan of verwijder gebruikers uit de uitsluitingslijst van een vertrouwd gebruikersdomein. Exporteer het serverlicentieverleningscertificaat naar een bestand dat met een andere RMS-installatie kan worden geïmporteerd.
-   **Sjablonen voor het rechtenbeleid configureren.** Klik op de koppeling om de webpagina Sjablonen voor het rechtenbeleid te openen. Hier kunt u sjablonen voor het rechtenbeleid van de onderneming maken en wijzigen.
-   **Logboekregistratie configureren.** Klik op de koppeling om de webpagina Logboekinstellingen te openen. Hier kunt u logboekregistratie in- of uitschakelen en de logboekserver en -database weergeven.
-   **De cluster-URL voor het extranet opgeven.** Klik op de koppeling om de webpagina Instellingen voor de cluster-URL voor extranet te openen. Hier kunt u de URL opgeven die moet worden gebruikt om vanaf het extranet toegang te krijgen tot certificeringservices van het basiscluster.
-   **Proxy-instellingen voor RMS opgeven.** Klik op de koppeling om de webpagina Proxy-instellingen van RMS te openen. Hier kunt u het adres van de proxyserver, het verificatietype en de gebruikersnaam opgeven die moeten worden gebruikt wanneer de RMS-server via een proxyserver verbinding moet maken met internet.
-   **Het aantal uitgegeven rechtenaccountcertificaten bijhouden.** Klik op de koppeling om de webpagina voor het bijhouden van rechtenaccountcertificaten te openen. Hier kunt u controleren hoeveel rechtenaccountcertificaten door het basiscluster zijn gedistribueerd. Zo kunt u inschatten hoeveel licenties voor clienttoegang u nodig hebt.
-   **Beveiligingsinstellingen beheren.** Klik op de koppeling om de webpagina Beveiligingsinstellingen te openen. Hier kunt u leden toevoegen aan of verwijderen uit de groep Supergebruikers en het wachtwoord voor de persoonlijke sleutel opnieuw instellen. Leden van de groep Supergebruikers beschikken over volledige bevoegdheden voor inhoud waarvoor een licentie is verleend.
-   **Instellingen voor accountcertificaten weergeven en configureren.** Klik op de koppeling om de webpagina Certificeringsinstellingen te openen. Hier kunt u de geldigheidsduur van het certificaat en/of de contactgegevens van een beheerder opgeven.
-   **Uitsluitingsbeleid inschakelen.** Klik op de koppeling om de pagina Uitsluitingsbeleid te openen. Hier kunt u uitsluitingsbeleid inschakelen dat is gebaseerd op versies van lockboxes, Windows-versies, accountcertificaten en toepassingen.
-   **Het serviceverbindingspunt registreren.** Klik op de koppeling om de webpagina Serviceverbindingspunt te openen. Hier kunt u het serviceverbindingspunt voor het cluster registreren en verwijderen.

Met MMC (Microsoft Management Console) kunnen beheerders ook andere taken uitvoeren zoals het controleren van gebeurtenissen en het beheren van Active Directory, IIS (Internet Information Services) en SQL Server.
