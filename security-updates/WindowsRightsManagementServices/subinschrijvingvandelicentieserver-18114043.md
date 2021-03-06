---
TOCTitle: Subinschrijving van de licentieserver
Title: Subinschrijving van de licentieserver
ms:assetid: '7bc63397-9186-464c-8824-867038adce9b'
ms:contentKeyID: 18114043
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747640(v=WS.10)'
---

Subinschrijving van de licentieserver
=====================================

Licentieservers worden tijdens het inrichten automatisch ingeschreven in een proces dat subinschrijving wordt genoemd. Als u echter een nieuwe server toevoegt aan een licentieservercluster, wordt de nieuwe server niet ingeschreven omdat voor deze server het serverlicentieverleningscertificaat en de configuratiedatabase van het cluster worden gebruikt.

In plaats van de subinschrijvingsaanvraag naar de inschrijvingsservice van Microsoft te versturen verstuurt de licentieserver de aanvraag naar de basiscertificeringsserver. De subinschrijvingsaanvraag voor een licentieserver is identiek aan de inschrijvingsaanvraag voor de basiscertificeringsserver.

Als de basiscertificeringsserver een subinschrijvingsaanvraag ontvangt, wordt gecontroleerd of de aanvraag correct is opgesteld. Vervolgens worden een certificaatketen waarin de licentiecertificaatketen van de basiscertificeringsserver is opgenomen, en een door de basiscertificeringsserver ondertekend certificaat teruggestuurd. Het certificaat bevat de openbare sleutel van de server die is ondertekend met de persoonlijke sleutel van de basiscertificeringsserver. Hiermee wordt aan de licentieserver het recht verleend gebruiks- en uitgiftelicenties uit te geven.

Het serverlicentiecertificaat is geldig voor één jaar. Het certificaat is geldig vanaf het moment dat het wordt uitgegeven. De geldigheid van het certificaat kan worden verlengd. Certificaten en licenties die door de server worden uitgegeven, zijn zeven jaar geldig. Deze certificaten en licenties zijn geldig vanaf het moment dat ze worden uitgegeven.

Standaard is de vereiste service voor het verwerken van een subinschrijvingsaanvraag op de basiscertificeringsserver, SubEnrollService.asmx, zo geconfigureerd dat alle toegang wordt geweigerd. Voordat een aanvraag kan worden verwerkt, moet u de DACL's wijzigen zodat RMS-beheerders toegang krijgen.
