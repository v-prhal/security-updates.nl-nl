---
TOCTitle: De accountcertificeringsservice opsporen
Title: De accountcertificeringsservice opsporen
ms:assetid: '293a2f91-4712-45ec-8b74-7533f4144cbd'
ms:contentKeyID: 18113858
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720224(v=WS.10)'
---

De accountcertificeringsservice opsporen
========================================

Met de accountcertificeringsservice van RMS worden rechtenaccountcertificaten verleend aan gebruikers. Elk rechtenaccountcertificaat (RAC) is alleen geldig voor een bepaalde computer of een bepaald apparaat. De gebruiker die dit certificaat aanvraagt, moet een geldig computercertificaat hebben.

De accountcertificeringsservice wordt alleen uitgevoerd op basiscertificeringsservers of -clusters. Als met een client een accountcertificering moet worden aangevraagd, moet eerst de URL voor de virtuele map Certification op de basiscertificeringsserver, waar de accountcertificeringsservice zich bevindt, uit Active Directory worden opgehaald. Vervolgens wordt het pad naar de accountcertificeringsservice toegevoegd.

De certificerings-URL van de basiscertificeringsserver wordt in Active Directory in de volgende notatie opgeslagen:

http://*servernaam*/\_wmcs/Certification

Als met een client een rechtenaccountcertificaat wordt aangevraagd, wordt de bestandsnaam van de accountcertificeringsservice als volgt toegevoegd aan de URL:

http://*servernaam*/\_wmcs/Certification/Certification.asmx

| ![](images/Cc720224.note(WS.10).gif)Opmerking                                     |
|----------------------------------------------------------------------------------------------------------------|
| Als u SSL hebt ingeschakeld op de RMS-server, wordt voor deze URL's het verbindingsprotocol https:// gebruikt. |
