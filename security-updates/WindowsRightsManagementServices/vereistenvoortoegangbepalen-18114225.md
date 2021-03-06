---
TOCTitle: Vereisten voor toegang bepalen
Title: Vereisten voor toegang bepalen
ms:assetid: 'eb2ce9a5-0430-4811-bd40-4a94a84426a8'
ms:contentKeyID: 18114225
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747790(v=WS.10)'
---

Vereisten voor toegang bepalen
==============================

Tijdens deze fase van de planning moet de omvang van de RMS-implementatie u bekend zijn. Bij het vaststellen van de beveiliging van uw RMS-systeem moet u de methoden bekijken waarmee u de reikwijdte voor de deelnemers kunt beperken, en ervoor zorgen dat de gegevens die zij met RMS beveiligen, ook worden beveiligd door de traditionele maatregelen voor het beveiligen van gegevens. U dient er ook voor te zorgen dat alleen vertrouwde beheerders de RMS-server kunnen beheren en configureren. U kunt de volgende methoden voor het beveiligen van de toegang bij RMS gebruiken:

-   **Toegangslijsten (ACL's)**. Elk van de RMS-webservices en de beheerwebsite kunnen worden beveiligd door toegangslijsten. Om ervoor te zorgen dat alleen gemachtigde gebruikers de RMS-service kunnen gebruiken kunt u de mogelijkheid van gebruikers om verbinding te maken met de RMS-certificerings- en licentieservices met behulp van toegangslijsten beperken. Dit kan van pas komen wanneer u wilt dat alleen bepaalde groepen beveiligde inhoud mogen maken of licenties voor beveiligde inhoud mogen ontvangen.
-   **Clientverificatie**. U kunt clients laten verifiëren met smartcards of op een andere manier wanneer een gebruiker probeert een gebruikslicentie of -certificaat aan te vragen. Hierdoor wordt de kans kleiner dat een onbevoegde gebruiker inhoud met behulp van een sessie van een gemachtigde gebruiker probeert te openen.
-   **Secure Sockets Layer**. Om een extra beveiligingslaag te maken kunt u ook een SSL-verbinding tussen de RMS-clients en de RMS-server tot stand brengen. U wordt aangeraden SSL in te schakelen en bij elk van de bestanden van RMS-webservices 128-bits codering te gebruiken. Dit zijn de ASMX-bestanden die in de virtuele mappen Licensing, Certification en Admin zijn opgenomen. Als u de webpagina's voor **RMS-beheer** wilt openen in een browser op een externe computer, moet u SSL inschakelen. Zelfs als SSL is ingeschakeld, dan nog kunt u de pagina **Algemeen beheer** niet op een externe computer openen.
    Zie de Help van IIS voor informatie over het configureren van SSL op servers.

In sommige organisaties is het nodig een beveiligd licentiesysteem per afdeling te maken dat niet door de andere afdelingen kan worden gebruikt. In een dergelijk scenario kan er een RMS-server worden gebruikt als middel voor het instellen van een IRM-beleid (information rights management). Als op een afdeling of in een vestiging van uw organisatie met extreem gevoelige inhoud wordt gewerkt, kunt u een aparte licentieserver of een apart licentiecluster voor deze afdeling of vestiging instellen, waarmee de licentieverlening en uitgifte van hun inhoud los van de rest van de organisatie kunnen worden beheerd. Een licentieserver wordt ingeschreven bij de basiscertificeringsserver of het basiscertificeringscluster waarmee certificeringsservices en andere services voor elke licentieserver worden uitgevoerd. Licentieservers bieden echter hun eigen licentie- en uitgifteservices.

Gebruikersaccounts, toegangslijsten en fysieke beveiliging zijn essentiële elementen in een implementatie. Voordat u RMS in een productieomgeving implementeert, moet u bepalen wat de beste beveiligingsmethode is en een geschikt beveiligingsmodel instellen.
