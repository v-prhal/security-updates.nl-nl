---
TOCTitle: De inschrijvingsservice opsporen
Title: De inschrijvingsservice opsporen
ms:assetid: 'bbeb00bd-04e0-4df6-8615-76aa8125b620'
ms:contentKeyID: 18114161
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747737(v=WS.10)'
---

De inschrijvingsservice opsporen
================================

De eerste RMS-server die in een forest moet worden ingericht, moet met de inschrijvingsservice van Microsoft worden verbonden voor de inschrijving en het verkrijgen van een serverlicentieverleningscertificaat. Het installatieprogramma van RMS verstuurt een UDDI-aanvraag voor de URL van de inschrijvingsservice naar de [UDDI-website van Microsoft](http://go.microsoft.com/fwlink/?linkid=14794) (http://go.microsoft.com/fwlink/?LinkId=14794). Voor de overige servers die als onderdeel van het basiscertificeringscluster worden ingericht, hoeven geen serverlicentiecertificaten te worden aangevraagd, omdat voor deze servers de configuratie van de eerste basiscertificeringsserver wordt gebruikt.
