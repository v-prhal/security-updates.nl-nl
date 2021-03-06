---
TOCTitle: Serverlicentieverleningscertificaten intrekken
Title: Serverlicentieverleningscertificaten intrekken
ms:assetid: '8020861d-d196-4431-8282-044675ef5616'
ms:contentKeyID: 18114016
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747578(v=WS.10)'
---

Serverlicentieverleningscertificaten intrekken
==============================================

Het kan voorkomen dat een organisatie een serverlicentieverleningscertificaat moet intrekken vanwege onvoorziene omstandigheden, waardoor er mogelijk kan worden ingebroken op de RMS-server. Als een persoonlijke sleutel niet in een hardwarebeveiligingsmodule wordt opgeslagen, is deze niet goed beveiligd tegen diefstal. In een organisatie kunnen serverlicentieverleningscertificaten en sleutels door een kwaadwillende persoon met toegang tot de server worden gewijzigd, of door een ontevreden werknemer worden gekopieerd of verwijderd. In dat geval kunt u intrekking implementeren om de schade te beperken en verder misbruik door een kwaadwillende gebruiker te voorkomen.

Standaard kan een licentie of certificaat worden ingetrokken door de principal waarmee de licentie of het certificaat is uitgegeven. Omdat door RMS-servers de licenties en certificaten voor uw beveiligde inhoud worden uitgegeven, kunt u deze zo nodig altijd intrekken. Als op een licentieserver is ingebroken, kunt u het serverlicentieverleningscertificaat van de server intrekken. Trekt u een serverlicentieverleningscertificaat in, dan worden de hiermee uitgegeven certificaten en licenties ongeldig. Zie '[Intrekking implementeren](https://technet.microsoft.com/4735f060-7197-4ae2-830a-f91bcc4de30a)' eerder in dit onderwerp voor instructies voor het intrekken van licenties en certificaten.

Het basiscertificeringscluster is echter een speciaal geval. Het serverlicentiecertificaat voor het basiscertificeringscluster wordt uitgegeven met de inschrijvingsservice van Microsoft en kan standaard alleen met deze service worden ingetrokken.

Microsoft kan uw serverlicentieverleningscertificaat alleen intrekken wanneer u over een gerechtelijk bevel beschikt en de openbare sleutel bekendmaakt aan het hof. Nadat Microsoft door het gerechtshof op de hoogte is gesteld dat er een bevel tot intrekking is uitgevaardigd, maakt Microsoft het serverlicentieverleningscertificaat bekend aan de hand van de openbare sleutel in de intrekkingslijst en wordt de lijst openbaar gemaakt. U kunt het gerechtshof verzoeken een intrekkingsbevel uit te vaardigen als de server waarvoor de licentie moet worden ingetrokken, voldoet aan de volgende voorwaarden:

-   U bent eigenaar van de server waarvan met de persoonlijke sleutel is geknoeid.
-   U bent eigenaar van de inhoud die door deze server wordt gepubliceerd en de publicatie van de inhoud is in strijd met de uw auteursrechten.

Volg de procedure in '[Intrekkingslijsten distribueren](https://technet.microsoft.com/e331338b-66d4-45e4-8d3f-acccf2302ac4)' eerder in dit gedeelte om van Microsoft intrekkingslijsten op te halen en te distribueren waarin het ingetrokken serverlicentieverleningscertificaat van een basiscertificeringsserver is opgenomen.

Als u de basiscertificeringsserver inricht, kunt u een openbare sleutel opgeven als instantie waarmee het serverlicentieverleningscertificaat van het basiscertificeringscluster kan worden ingetrokken. Deze openbare sleutel kan van de organisatie of van een derde partij zijn. Met een intrekkingslijst die is ondertekend met de bijbehorende persoonlijke sleutel kan het serverlicentieverleningscertificaat worden ingetrokken.

Als u het serverlicentieverleningscertificaat van de basiscertificeringsserver wilt intrekken, maakt u een intrekkingslijst waarin dit serverlicentieverleningscertificaat is opgegeven, ondertekent u de lijst met de persoonlijke sleutel van uw organisatie of de derde partij en distribueert u de intrekkingslijst naar alle gebruikers. Zie 'Intrekkingslijsten van de organisatie distribueren' in '[Intrekkingslijsten distribueren](https://technet.microsoft.com/e331338b-66d4-45e4-8d3f-acccf2302ac4)' eerder in dit onderwerp voor instructies.

U kunt een serverlicentieverleningscertificaat in een intrekkingslijst intrekken met de volgende parameters:

-   **GUID**. Een serverlicentieverleningscertificaat kan op basis van zijn GUID (Globally Unique Identifier) worden ingetrokken. Zie 'Certificaten en licenties intrekken op basis van de GUID' in '[Intrekkingslijsten maken](https://technet.microsoft.com/1ef75199-3344-4225-84de-a863a777696a)' eerder in dit onderwerp voor meer informatie over het gebruik van deze parameter in een intrekkingslijst.
-   **Hashwaarde**. Een serverlicentieverleningscertificaat kan worden ingetrokken op basis van een SHA-1-hash van de Unicode-tekens in de tekst van het certificaat. Zie 'Certificaten en licenties intrekken op basis van de hashwaarde' in '[Intrekkingslijsten maken](https://technet.microsoft.com/1ef75199-3344-4225-84de-a863a777696a)' eerder in dit onderwerp voor meer informatie over het gebruik van deze parameter in een intrekkingslijst.

Als u het serverlicentieverleningscertificaat van een RMS-installatie wilt ophalen, moet u een query uitvoeren op de RMS-configuratiedatabase. In de volgende procedure wordt beschreven hoe u deze gegevens ophaalt uit een SQL-configuratiedatabase en opslaat naar een bestand dat eenvoudig kan worden gelezen in een browser:

1.  Open SQL Query Analyzer en maak een verbinding met de configuratiedatabase van de basiscertificeringsserver.
2.  Klik in het menu **Query** op **Results in Text**.
3.  Klik in het menu **Tools** op **Options** om het dialoogvenster **Options** te openen. Klik op de tab **Results** en stel **Maximum characters per column** in op **8192**.
        ```
1.  Kopieer de resultaten uit het venster **Results** naar een teksteditor zoals Kladblok. Sla de resultaten op in een XML-bestand.

Zie '[Intrekkingslijsten maken](https://technet.microsoft.com/1ef75199-3344-4225-84de-a863a777696a)' eerder in dit onderwerp voor meer informatie over de wijze waarop u deze gegevens in een intrekkingslijst gebruikt.

Als u de gegevens in het serverlicentieverleningscertificaat hebt opgeslagen als XML-bestand, kunt u als volgt de openbare sleutel ophalen:

1.  Open het XML-bestand met het serverlicentieverleningscertificaat in een XML- of teksteditor.
2.  Kopieer in het gedeelte &lt;ISSUEDPRINCIPALS&gt; het element &lt;PUBLICKEY&gt;.
3.  Sla deze gegevens op in een bestand dat u aan de rechtbank kunt overleggen of in een intrekkingslijst voor de organisatie kunt plaatsen.

Als het serverlicentieverleningscertificaat van het basiscertificeringscluster is ingetrokken, zijn de met uw RMS-installatie uitgegeven certificaten en licenties niet meer geldig voor de inhoud waarvoor een intrekkingslijst is vereist en is de inhoud niet langer toegankelijk. Het type licentiecertificaat van de gebruiker heeft geen invloed op deze procedure. Als u de inhoud wilt behouden die door deze server, waarvan de licentie wordt ingetrokken, werd gepubliceerd, moet u een van de volgende handelingen uitvoeren voordat u de intrekkingslijst implementeert:

-   Sla de inhoud op zonder RMS-beveiliging.
-   Publiceer de inhoud opnieuw zonder vereisten voor intrekkingslijsten.

Zowel bij intrekking door Microsoft als bij intrekking door een derde partij is de intrekkingslijst van toepassing op alle koppelingsaanvragen, omdat de lijst is ondertekend met de persoonlijke sleutel van een principal uit de vertrouwensketen van de gebruikslicentie. Als gevolg daarvan mislukken alle koppelingsaanvragen waarin gebruikslicenties zijn opgenomen die door de RMS-installatie zijn uitgegeven met het ingetrokken serverlicentieverleningscertificaat.

| ![](images/Cc747578.note(WS.10).gif)Opmerking                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------|
| Microsoft zal een serverlicentieverleningscertificaat echter alleen intrekken wanneer hiertoe opdracht wordt gegeven door een rechtbank. |
