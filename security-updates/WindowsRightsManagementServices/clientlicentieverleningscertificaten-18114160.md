---
TOCTitle: Clientlicentieverleningscertificaten
Title: Clientlicentieverleningscertificaten
ms:assetid: 'bfb36387-3e15-4cde-8b8f-482219569a64'
ms:contentKeyID: 18114160
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747744(v=WS.10)'
---

Clientlicentieverleningscertificaten
====================================

Met een clientlicentieverleningscertificaat beschikt een auteur over het recht door RMS beveiligde inhoud uit te geven zonder dat er verbinding is met het bedrijfsnetwerk.

Als een auteur een clientlicentiecertificaat wil verkrijgen, moet deze vanaf een clientcomputer een clientinschrijving bij de basiscertificeringsserver of de licentieserver aanvragen. Vervolgens wordt vanaf de server een clientlicentiecertificaat teruggestuurd voor die computer.

Een clientlicentiecertificaat bevat de openbare en persoonlijke sleutel van de clientlicentie. De persoonlijke sleutel is gecodeerd met de openbare sleutel van de auteur die het certificaat heeft aangevraagd. Daarnaast bevat het certificaat de openbare sleutel van de server waarmee het certificaat is uitgegeven. Deze sleutel is ondertekend met de persoonlijke sleutel van de server waarmee het certificaat is uitgegeven. De persoonlijke sleutel van de clientlicentie wordt gebruikt voor het ondertekenen van uitgiftelicenties die door de auteur worden gemaakt.
