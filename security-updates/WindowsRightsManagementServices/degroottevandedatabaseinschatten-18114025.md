---
TOCTitle: De grootte van de database inschatten
Title: De grootte van de database inschatten
ms:assetid: '87652cc2-b886-4797-8d40-356669768089'
ms:contentKeyID: 18114025
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747585(v=WS.10)'
---

De grootte van de database inschatten
=====================================

Wanneer u een inschatting gaat maken van de opslagcapaciteit voor de RMS-databases, neemt u in eerste instantie een opslag van minimaal 10 megabytes (MB) en voegt u voor elke 500 gebruikers van de RMS-configuratiedatabase 1 MB toe De logboekdatabase kan op een andere databaseserver dan de configuratiedatabase staan.

Als u de logboekregistratie van RMS gebruikt, is er voor iedere gebruiker 1 MB nodig tijdens de eerste certificeringsfase van de gebruikers wanneer een groot aantal gebruikers zich aanmelden. Wanneer uw implementatie bijvoorbeeld 1000 gebruikers kan verwerken, wordt de logboekdatabase 1 gigabyte (GB) groot, omdat iedere gebruiker wordt geactiveerd en gecertificeerd door de RMS-certificeringsserver. Onder normale omstandigheden wordt de logboekdatabase elke dag voor iedere gebruiker 200 kilobytes (kB) groter. (Bij een gefaseerde implementatie is er voor iedere nieuwe gebruiker ongeveer 1 MB nodig.)
