---
TOCTitle: De subinschrijvingsservice opsporen
Title: De subinschrijvingsservice opsporen
ms:assetid: 'b159953a-af38-4a9e-8c87-1aff5fb4e366'
ms:contentKeyID: 18114111
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747641(v=WS.10)'
---

De subinschrijvingsservice opsporen
===================================

Voor een afzonderlijke licentieserver of de eerste licentieserver in een cluster moet een subinschrijvingsaanvraag naar de RMS-basiscertificeringsserver worden verstuurd en een serverlicentieverleningscertificaat worden opgehaald. De licentieserver krijgt de URL van de subinschrijvingsservice van de basiscertificering op de volgende wijze:

Tijdens het inrichten van een licentieserver wordt Active Directory in het installatieprogramma van RMS doorzocht op het serviceverbindingspunt van het basiscertificeringscluster. In RMS wordt de URL in het serviceverbindingspunt gebruikt voor het bepalen van de locatie van het basiscertificeringscluster. Vervolgens wordt er een aanvraag voor een serverlicentieverleningscertificaat van de subinschrijvingsservice van de basiscertificeringsserver verstuurd.

Als met een licentieserver een inschrijvingsservice moet worden aangevraagd, moet eerst de URL voor de virtuele map Certification op de basiscertificeringsserver, waar de inschrijvingsservice zich bevindt, uit de Active Directory worden opgehaald. Vervolgens wordt het pad aan de subinschrijvingsservice toegevoegd.

De URL voor de virtuele map Certification op de basiscertificeringsserver wordt in Active Directory met de volgende notatie opgeslagen:

http://*servernaam*/\_wmcs/Certification

Wanneer de subinschrijvingsservice met een licentieserver wordt aangevraagd, wordt de bestandsnaam van de service als volgt toegevoegd aan de URL:

http://servernaam/\_wmcs/Certification/SubEnrollService.asmx

| ![](images/Cc747641.note(WS.10).gif)Opmerking                                     |
|----------------------------------------------------------------------------------------------------------------|
| Als u SSL hebt ingeschakeld op de RMS-server, wordt voor deze URL's het verbindingsprotocol https:// gebruikt. |
