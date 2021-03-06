---
TOCTitle: Servers toevoegen aan een bestaande installatie
Title: Servers toevoegen aan een bestaande installatie
ms:assetid: '7f3598ff-cd19-4daa-aa65-877f7f95a8ec'
ms:contentKeyID: 18114047
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747648(v=WS.10)'
---

Servers toevoegen aan een bestaande installatie
===============================================

Indien nodig kunt u servers aan uw RMS-installatie toevoegen om te voorzien in een toegenomen vraag of om servers te vervangen die uit bedrijf moeten worden genomen. In elke RMS-installatie moet minstens één basiscertificeringsserver aanwezig zijn. Een cluster kan meerdere basiscertificeringsservers bevatten. In een RMS-installatie kunnen tevens zelfstandige of geclusterde licentieservers worden opgenomen.

Met elk van de volgende methoden kunt u servers toevoegen aan een RMS-installatie:

-   Een of meer RMS-servers toevoegen aan een basiscertificeringscluster.
-   Een nieuwe, zelfstandige licentieserver toevoegen.
-   Een of meer RMS-servers toevoegen aan een licentiecluster.

**Basiscertificeringsservers toevoegen**

In de meeste gevallen kunt u de beschikbaarheid en redundantie van uw implementatie het beste verbeteren door een of meer RMS-servers toe te voegen aan een basiscertificeringscluster. Een basiscertificeringscluster bestaat uit een of meer basiscertificeringsservers. In tegenstelling tot licentieservers, die alleen licentie- en uitgifteservices leveren, bieden basiscertificeringsservers alle RMS-services.

Tijdens het installeren en inrichten kunt u een server toevoegen aan een cluster. Als u dit doet, wordt de nieuwe RMS-server automatisch geconfigureerd als een clusterlid. Zie '[RMS met Service Pack 1 installeren](https://technet.microsoft.com/dab20175-a690-43f8-b943-768d289daa0d)' en '[Een server toevoegen aan een cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)' voor stapsgewijze instructies voor het installeren en inrichten van een RMS-server die aan het basiscertificeringscluster moet worden toegevoegd.

De eerste keer dat u een cluster maakt, moet u mogelijk ook software of hardware voor clusters en taakverdeling instellen. Als u al een cluster hebt geïmplementeerd, moet u de software of hardware voor taakverdeling configureren voor het nieuwe clusterlid.

**Licentieservers toevoegen**

In tegenstelling tot de basiscertificeringsserver, waarmee alle RMS-services worden geleverd, bieden licentieservers alleen licentie- en uitgifteservices.

Licentieservers zijn optioneel en worden doorgaans geïmplementeerd om aan bepaalde licentievereisten te voldoen, zoals in de volgende gevallen:

-   Wanneer unieke vereisten voor het rechtenbeheer van een afdeling moeten worden ondersteund. Het is bijvoorbeeld mogelijk dat voor een afdeling in uw organisatie andere beveiligingsvereisten voor rechtenbeheer gelden dan voor de rest van de organisatie en dat de implementatie van licenties voor deze afdeling volledig moet worden beheerd door deze afdeling. Omdat in een forest slechts één basiscertificeringsserver is toegestaan, is een aparte basiscertificeringsserver waarschijnlijk geen optie. In dat geval kunt u een licentieserver of licentiecluster instellen op basis van de vereisten van deze groep. U kunt dan een apart rechtenbeleid instellen voor deze licentieserver of dit licentiecluster.
-   Wanneer het rechtenbeheer voor externe bedrijfspartners moet worden ondersteund via een extranet waarvoor een sterke scheiding en tracering van bronnen is vereist voor bepaalde bedrijfspartners. Zie '[Een extranet-URL configureren](https://technet.microsoft.com/88fec9ff-c96c-4d20-8856-0485e7507572)' verderop in dit onderwerp voor meer informatie.
-   Wanneer de licentietaken van de basiscertificeringsserver moeten worden overgenomen, zodat deze wordt ontlast. In organisaties met één basiscertificeringsserver (in plaats van een basiscertificeringscluster) kan dit resulteren in betere prestaties.

In de meeste gevallen kunt u RMS-servers het beste aan het basiscertificeringscluster toevoegen, zodat u redundantie en taakverdeling kunt instellen voor alle servers in de implementatie. Hoewel licentieservers ook kunnen worden gebruikt om de verwerking van licentie- en uitgifteaanvragen over te nemen, kunnen licentieservers geen taken overnemen van het basiscertificeringscluster. Tenzij er een bepaalde behoefte bestaat om aparte licentieservers te implementeren, kunt u taakverdeling het beste voor alle RMS-servers instellen door deze op te nemen in het basiscertificeringscluster.

Zie '[RMS met Service Pack 1 installeren](https://technet.microsoft.com/dab20175-a690-43f8-b943-768d289daa0d)' en '[Een licentieserver inrichten](https://technet.microsoft.com/4d67b898-0ba9-4eef-ab7d-ee0ca55a688e)' voor stapsgewijze instructies voor het installeren en inrichten van een RMS-licentieserver.
