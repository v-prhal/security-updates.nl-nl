---
TOCTitle: RMS in andere forests implementeren
Title: RMS in andere forests implementeren
ms:assetid: 'd531dfdc-efff-4eb0-8d99-f1fd19d7a963'
ms:contentKeyID: 18114146
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747685(v=WS.10)'
---

RMS in andere forests implementeren
===================================

Als in uw organisatie meerdere Active Directory-forests aanwezig zijn en u het gebruik van RMS in uw organisatie wilt doorvoeren, moet u het netwerk zo configureren dat in RMS gebruikersaccounts en distributiegroepen uit andere forests kunnen worden geïdentificeerd en geverifieerd.

In RMS wordt Active Directory gebruikt voor het identificeren van gebruikers en distributiegroepen. Als in de Active Directory-implementatie van de organisatie meerdere forests zijn opgenomen, worden in RMS contactobjecten gebruikt om de identiteit van gebruikers en groepen uit een andere forest dan die van de RMS-server te achterhalen. Er zijn drie dingen nodig om dit te realiseren:

1.  In het andere forest moeten RMS-certificeringsservers aanwezig zijn en voor elke externe groep moeten contactobjecten worden gedefinieerd.
2.  Er moeten schema-uitbreidingen zijn in forests met contactobjecten waarmee zij kunnen terugwijzen naar de forests waarin de eigenlijke objecten staan.
3.  De kenmerken in de contactobjecten moeten zijn gesynchroniseerd en terugwijzen naar het forest waarin het eigenlijke object voorkomt.

Stel bijvoorbeeld dat groepen in het ene forest en gebruikers in een ander forest worden ingesteld en beheerd. Een gebruiker wil op basis van het lidmaatschap in een bepaalde groep rechten aan inhoud toewijzen. In dit scenario is *RMS\_Server\_U* de server in het forest met de gebruikersaccounts en is *RMS\_Server\_G* de server in het forest met de groepsaccounts. Er is een vertrouwd gebruikersdomein tussen deze twee RMS-servers ingesteld. In *RMS\_Server\_U* kan het groepslidmaatschap dat in de uitgiftelicentie is opgegeven, alleen naar andere forests worden uitgebreid als in het lokale Active Directory-forest een contactobject is opgenomen dat de groep in het externe forest vertegenwoordigt. In RMS kunnen de kenmerken van het contactobject worden opgezocht en worden bekeken of dit object een groep uit een andere forest vertegenwoordigt. Ook kan er in dat forest naar een RMS-server worden gezocht en worden vastgesteld of er een vertrouwensrelatie met de andere RMS-server is. Wanneer *RMS\_Server\_U* in Active Directory zoekt naar de groep die is opgegeven in de uitgiftelicentie, zal het contactobject aangeven dat de groep bij een ander forest hoort. Wanneer *RMS\_Server\_U* de aanvraag doorstuurt naar de RMS-server die in het serviceverbindingspunt voor dat domein staat, identificeert het serviceverbindingspunt *RMS\_Server\_G* als de RMS-certificeringsserver voor het domein. *RMS\_Server\_U* zoekt vervolgens in *RMS\_Server\_G* naar het lidmaatschap voor de groep.

**msExchOriginatingForest** is het kenmerk dat in RMS voor deze informatie wordt opgezocht. Dit kenmerk wordt standaard in het Active Directory-schema geïnstalleerd als u Exchange Server 2003 in het forest hebt geïnstalleerd. Dit kenmerk moet aanwezig zijn in het forest van elk Active Directory-schema dat wordt gebruikt in RMS. Als u Exchange Server 2003 niet gebruikt, kunt u deze schema-uitbreidingen toevoegen door de beheer-toolkit van RMS te downloaden. De toolkit bevat een schemabestand en instructies voor het toevoegen van dit bestand aan Active Directory.

Deze kenmerken moeten worden gesynchroniseerd, zodat de contactobjecten naar het eigenlijke object in andere forests wijzen. Nadat u het kenmerk aan het Active Directory-schema hebt toegevoegd, moet u de waarde van dat kenmerk configureren als de FQDN-naam (Fully Qualified Domain Name) van het forest waarin de groep is opgenomen, bijvoorbeeld corp.fabrikam.com.

U kunt dit uitvoeren met behulp van Microsoft Identity Integration Server (MIIS) 2003 of Identity Integration Feature Pack (IIFP) en de beheeragent voor de globale adreslijst (GAL) van Active Directory.

U moet voor de lokale RMS-server machtigingen instellen waarmee een externe Active Directory kan worden doorzocht en de .NET Remoting-interfaces uit de externe RMS-installatie kunnen worden aangeroepen.

Als u groepsuitbreiding naar andere forests wilt ondersteunen, moeten tevens lees- en schrijfmachtigingen voor Active Directory worden ingesteld voor de account die in de forests als RMS-serviceaccount wordt gebruikt. In RMS wordt aan alle geverifieerde gebruikers met domeinreferenties automatisch leestoegang tot Active Directory verleend. Ter verhoging van de beveiliging kunt u deze toegang uit de DACL verwijderen en vervangen door de serviceaccounts van de verschillende forests.

Welke machtigingen voor de RMS-serviceaccount vereist zijn, hangt af van eventuele Active Directory-vertrouwensrelaties tussen de lokale en externe forests. Hieronder worden de vertrouwensmodellen en de vereiste machtigingen beschreven:

-   **Er is wederzijds vertrouwen**. Er bestaat een vertrouwensrelatie tussen het lokale RMS-forest en het forest waaruit de groep afkomstig is. De RMS-serviceaccount die in elk forest voor de RMS-server is opgenomen, kan elke geldige domeinaccount uit het forest zijn. Voeg de lokale RMS-serviceaccount toe aan de DACL in de map \\Inetpub\\wwwroot\\\_wmcs\\drmRemote op alle RMS-servers in het forest waaruit de groep afkomstig is.
-   **Er is geen wederzijds vertrouwen**. Het lokale RMS-forest vertrouwt het forest waaruit de groep afkomstig is, maar dat vertrouwen is niet wederzijds. De RMS-serviceaccount voor alle RMS-servers in de organisatie moet zijn gebaseerd op een geldige domeinaccount uit het vertrouwde forest. Voeg deze account op alle RMS-servers in het forest waaruit de groep afkomstig is, toe aan de DACL van de map \\Inetpub\\wwwroot\\\_wmcs\\drmRemote.
-   **Er is geen vertrouwen**. De forests in de organisatie kunnen gebruikers en groepen uit andere forests niet verifiëren. U wordt aangeraden geen groepsuitbreiding in forests te gebruiken als de betrokken forests geen vertrouwensrelatie hebben. Als het voor de werking van het systeem wel moet, kunt u dit scenario inschakelen door de RMS-serviceaccount als een geldige domeinaccount in beide forests te configureren, met voor elk forest dezelfde gebruikersnaam en hetzelfde wachtwoord. Daarnaast moet op elke front-endserver een lokale computeraccount worden gemaakt die dezelfde gebruikersnaam en hetzelfde wachtwoord heeft als de domeinaccounts die worden gebruikt voor de RMS-serviceaccounts in beide forests. Op deze manier zijn voor de lokale service automatisch voldoende machtigingen ingesteld om zowel het externe Active Directory als het externe RMS te verifiëren.

Vertrouwensbeleid van RMS gebruiken
-----------------------------------

Wanneer RMS in een organisatie met meerdere forests wordt geïmplementeerd, moet er in elk forest dat als host fungeert voor gebruikersaccounts die in het RMS-systeem worden gebruikt, een RMS-certificeringsserver worden geïmplementeerd. Als gebruikers in andere forests door RMS beveiligde inhoud moeten kunnen gebruiken, moet u het vertrouwensbeleid van RMS configureren, zodat de certificaten en licenties die op de andere RMS-server worden gegenereerd, kunnen worden vertrouwd. Er zijn twee typen vertrouwensbeleid die bij RMS kunnen worden gebruikt: vertrouwde gebruikersdomeinen en vertrouwde uitgiftedomeinen. Bij vertrouwde gebruikersdomeinen kan een RMS-server de rechtenaccountcertificaten vertrouwen die door een andere RMS-certificeringsserver zijn gegenereerd, en vanaf de andere server gebruikslicenties aan gebruikers met rechtenaccountcertificaten uitgeven. Bij vertrouwde uitgiftedomeinen kan een RMS-server gebruikslicenties genereren op basis van uitgiftelicenties waarmee de andere licentieserver wordt opgegeven.

Er zijn een aantal opties voor de manier waarop u met vertrouwensbeleid meerdere forests kunt ondersteunen:

-   Een RMS-certificeringscluster in elk forest met één licentiecluster dat door alle gebruikers wordt gebruikt. Het RMS-licentiecluster wordt geconfigureerd met een vertrouwd gebruikersdomein waarin zich alle RMS-certificeringsclusters bevinden. De RMS-clients worden geconfigureerd met behulp van een registersleutel en maken verbinding met het licentiecluster waar de gebruikslicenties worden opgehaald.
-   Een RMS-certificerings- en licentiecluster in elk forest met een vertrouwd gebruikersdomein. Dit domein is op elk cluster zo ingesteld dat het de RMS-servers in de andere forests vertrouwt. Iedere gebruiker gebruikt de RMS-server in zijn of haar forest voor het ophalen van gebruikslicenties en kan de licentieserver opzoeken via het serviceverbindingspunt in Active Directory.
-   Als de gebruikers van door RMS beveiligde inhoud onderdeel zijn van een forest dat geen toegang heeft tot de forest vanwaar de inhoud is uitgegeven, kan er een vertrouwd uitgiftedomein worden ingesteld waarmee een licentie voor de inhoud kan worden verstrekt en de inhoud kan worden gebruikt. Voor vertrouwde uitgiftedomeinen moet de persoonlijke sleutel van de RMS-server waar vanaf de inhoud is uitgegeven, worden geïmporteerd.

Zie 'Vertrouwensrelaties en vertrouwensbeleid beheren' in 'Een RMS-server beheren' in deze documentatie voor meer informatie over het configureren van een vertrouwensbeleid.
