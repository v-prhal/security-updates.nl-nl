---
TOCTitle: Alternatieven voor het uit bedrijf nemen van RMS
Title: Alternatieven voor het uit bedrijf nemen van RMS
ms:assetid: '4d32f35e-997d-4d10-ab66-efe217e853f7'
ms:contentKeyID: 18113915
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720268(v=WS.10)'
---

Alternatieven voor het uit bedrijf nemen van RMS
================================================

Als u RMS in uw organisatie wilt blijven gebruiken maar om een of andere reden bepaalde RMS-servers moet stopzetten, kunt u de volgende alternatieven voor het uit bedrijf nemen overwegen.

**Een vertrouwd uitgiftedomein instellen**

Alle door RMS beveiligde informatie wordt gecodeerd door de persoonlijke sleutel van de RMS-server. Met een vertrouwd uitgiftedomein kunt u de persoonlijke sleutel van de ene RMS-server naar een andere RMS-server overbrengen. Zo kan een RMS-server gebruikslicenties uitgeven op basis van uitgiftelicenties die door een andere RMS-server zijn gemaakt. Nadat de sleutel is geëxporteerd, kan de inrichting en installatie van de server ongedaan worden gemaakt.

**Een groep supergebruikers instellen**

Als door RMS beveiligde inhoud niet kan worden geopend omdat er geen gebruikers zijn die daarvoor zijn gemachtigd, kunt u de volledige controle over alle door RMS beveiligde inhoud die door die server is uitgegeven, aan de groep supergebruikers overdragen. Aan de leden van de groep supergebruikers worden volledige eigenaarsrechten toegewezen voor alle gebruikslicenties die worden uitgegeven door de RMS-server of het RMS-cluster waarvoor de groep supergebruikers is geconfigureerd. Dit betekent dat leden van deze groep alle beveiligde inhoudsbestanden kunnen decoderen en de beveiliging kunnen opheffen. Een lid van deze groep kan bijvoorbeeld de beveiliging opheffen voor bestanden die zijn uitgegeven door een ontslagen medewerker, zodat een nieuwe eigenaar de bestanden kan uitgeven en beheren.

De groep supergebruikers bevat standaard geen leden, zelfs geen beheerders. Deze groep moet binnen Active Directory als een distributiegroep voorkomen met een e-mailadres dat dezelfde waarde heeft als de naam van de groep, in de notatie *groepsnaam*@*domeinnaam*.com. De naam van de groep moet exact overeenkomen met het kenmerk van het e-mailadres en is hoofdlettergevoelig.
