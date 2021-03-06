---
TOCTitle: 'Praktische tips voor RMS-beheer'
Title: 'Praktische tips voor RMS-beheer'
ms:assetid: '385f8112-da00-417f-a2b8-42dc1e06b717'
ms:contentKeyID: 18113936
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720245(v=WS.10)'
---

Praktische tips voor RMS-beheer
===============================

Hieronder staan enkele tips voor het beheren van RMS.

-   **Implementeer geen andere services op RMS-servers**
    Als u andere services dan de RMS-services uitvoert op uw servers, kunnen er conflicten optreden die kunnen resulteren in beveiligingsproblemen. Gebruik prestatiemeteritems om te controleren of de service minder gaat functioneren en er geen conflict optreedt.
-   **Maak regelmatig back-ups van de configuratiedatabases**
    In de configuratiedatabases wordt informatie opgeslagen die cruciaal is voor het functioneren van RMS. Daarnaast worden in de configuratiedatabase van het basiscertificeringscluster de sleutelparen voor de volledige installatie opgeslagen. Als u regelmatig back-ups maakt, kunt u RMS snel herstellen als een databaseserver uitvalt. Daarnaast is het ook raadzaam de geldigheid van deze back-ups te testen door de bestanden in een afzonderlijke testomgeving te herstellen. Zie 'Een back-up van het RMS-systeem maken en het RMS-systeem herstellen' in het gedeelte 'Een RMS-implementatie plannen' van deze documentatie voor meer informatie.
-   **Verklein regelmatig de logboekdatabase**
-   **Gebruik Microsoft Operations Manager (MOM) voor het controleren van de RMS-server**
    Gebruik MOM en RMS MOM Pack om kritische gebeurtenissen te onderscheppen en een afname van de prestaties te detecteren en daarvan meldingen te geven.
