---
TOCTitle: Redundantie en taakverdeling verzorgen
Title: Redundantie en taakverdeling verzorgen
ms:assetid: '162d547c-78a7-4848-b43e-58e481832af2'
ms:contentKeyID: 18113843
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720199(v=WS.10)'
---

Redundantie en taakverdeling verzorgen
======================================

Als u er zeker van wilt zijn dat gebruikers altijd licenties kunnen aanvragen en inhoud kunnen publiceren wanneer dat nodig is, kunt u het beste redundante RMS-servers inzetten door clusters te gebruiken. Dit houdt in dat u een basiscertificeringscluster moet opzetten die ten minste uit twee servers bestaat. Als u tevens een afzonderlijke licentieserver inzet ter ondersteuning van de specifieke licentieverleningsbehoeften van een individuele groep binnen uw organisatie, moet u de licentieserver eveneens uitvoeren als een cluster van ten minste twee servers.

De verschillende fysieke servers van het basiscertificeringscluster of van een licentiecluster vormen een 'webkudde' achter een gedeelde URL of virtueel adres. Als er binnen uw organisatie een serverfarm wordt gebruikt, kunt u RMS integreren in de techniek die u voor virtuele adressering gebruikt, zoals Round Robin-DNS, de Network Load Balancing-service of een speciale hardwareoplossing.

Naast taakverdeling is het gunstig virtuele adressering te gebruiken in combinatie met RMS, omdat het systeem zodoende niet meer afhankelijk is van één fysieke server voor het verlenen van certificerings- of licentieverleningsservices. Geen enkele computer van een eindgebruiker hoeft dus rechtstreeks toegang te hebben tot welke server dan ook die zich binnen een cluster bevindt.
