---
TOCTitle: De introductiepagina van de beheerwebsite gebruiken
Title: De introductiepagina van de beheerwebsite gebruiken
ms:assetid: '6c155977-bd0e-47d6-ac65-1746cddb505e'
ms:contentKeyID: 18113970
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720290(v=WS.10)'
---

De introductiepagina van de beheerwebsite gebruiken
===================================================

Op de **introductiepagina van de beheerwebsite** kunt u informatie over de server of het cluster weergeven en hebt u toegang tot de beheeropties. Deze pagina is alleen beschikbaar als de server is ingericht.

Als u deze webpagina wilt openen vanaf de server die u wilt beheren, gaat u als volgt te werk:

1.  Meld u aan als lokale beheerder.
2.  Klik op **Start**, wijs **Alle programma's** en **Windows RMS** aan en selecteer vervolgens **Windows RMS-beheer**.
3.  Klik op de pagina **Algemeen beheer** op **RMS op deze website beheren**.

Als u beheer op afstand hebt ingeschakeld met SSL, kunt u de **introductiepagina van de beheerwebsite** ook openen op een andere computer. Hierbij gaat u als volgt te werk:

1.  Typ het volgende webadres op de adresbalk van de webbrowser:
    https://*clusternaam:poortnummer*/\_wmcs/admin
    Hierbij is *clusternaam:poortnummer* de URL die u tijdens het inrichten hebt opgegeven voor dit cluster. Geef het poortnummer alleen op als u een andere poort dan standaardpoort 80 hebt opgegeven.
2.  Wanneer hierom wordt gevraagd, typt u de referenties van een lokale beheerder op de server die u opent.

Op de **introductiepagina van de beheerwebsite** wordt informatie over het cluster weergegeven, zoals de cluster-URL, de naam en locatie van de configuratiedatabase en de verloopdatum van het serverlicentieverleningscertificaat. Daarnaast zijn op deze pagina koppelingen naar pagina's opgenomen waar u de volgende beheeropties kunt configureren voor het cluster:

-   **Vertrouwensbeleid.** Hiermee kunt u vertrouwde domeinen toevoegen en verwijderen. Zie '[Vertrouwensrelaties en vertrouwensbeleid beheren](https://technet.microsoft.com/1c96ee74-fd28-4511-be21-087e2b04c3ee)' verderop in dit onderwerp voor meer informatie.
-   **Sjablonen voor het rechtenbeleid**. Hiermee maakt en wijzigt u sjablonen voor het rechtenbeleid. Zie '[Sjablonen voor het rechtenbeleid beheren](https://technet.microsoft.com/718286dc-3399-4556-96c9-ec3a33d31877)' verderop in dit onderwerp voor meer informatie.
-   **Logboekinstellingen**. Hiermee kunt u logboekregistratie in- en uitschakelen en de naam van de logboekserver en -database weergeven. Zie '[Logboekregistratie beheren](https://technet.microsoft.com/8fccfc57-2135-494e-8e44-f6191bf5e4a0)' verderop in dit onderwerp voor meer informatie.
-   **Instellingen voor de cluster-URL voor extranet.** Hiermee geeft u een op afstand beschikbare URL op voor aanvragen voor licenties en accountcertificaten. Zie '[Een extranet-URL configureren](https://technet.microsoft.com/88fec9ff-c96c-4d20-8856-0485e7507572)' verderop in dit onderwerp voor meer informatie.
-   **RMS-proxyinstellingen.** Geef het adres van de proxyserver, het verificatietype en de gebruikersnaam op die moeten worden gebruikt wanneer de RMS-server via een proxyserver verbinding moet maken met internet. Zie '[Proxyinstellingen voor RMS configureren](https://technet.microsoft.com/179d2970-62e9-4487-aa5b-f4334234991e)' verderop in dit onderwerp voor meer informatie.
-   **Beveiligingsinstellingen.** Hiermee stelt u het wachtwoord voor de persoonlijke sleutel van de server opnieuw in, geeft u de groep supergebruikers op waarvan de leden alle gelicentieerde inhoud kunnen decoderen, en neemt u RMS uit bedrijf. Zie '[Beveiliging bij gebruik van RMS beheren](https://technet.microsoft.com/62050812-de4f-4392-8d63-f2f89aa01ed4)' verderop in dit onderwerp voor meer informatie.
-   **Certificeringsinstellingen.** Hiermee geeft u de geldigheidsduur voor rechtenaccountcertificaten en de contactgegevens van een beheerder op. Deze optie is alleen beschikbaar in het basiscertificeringscluster, niet op licentieservers. Zie '[Rechtenaccountcertificaten beheren](https://technet.microsoft.com/49c5c2ba-e197-4e4b-b3b3-b3248f068bcc)' verderop in dit onderwerp voor meer informatie.
-   **Uitsluitingsbeleid.** Hiermee stelt u uitsluiting in op basis van de versie van de lockbox, het rechtenaccountcertificaat, de Windows-versie of de toepassing met RMS-ondersteuning. Zie '[Uitsluitingsbeleid beheren](https://technet.microsoft.com/ee31e099-e095-4648-95da-0009fbeb48cb)' verderop in dit onderwerp voor meer informatie.
-   **RM-accountcertificeringsrapport.** Hiermee geeft u weer hoeveel rechtenaccountcertificaten zijn uitgegeven. Deze optie is alleen beschikbaar in het basiscertificeringscluster, niet op licentieservers. Zie '[Rechtenaccountcertificaten traceren](https://technet.microsoft.com/5bb0f3cf-fc44-4e60-a93f-c789d6f8a902)' verderop in dit onderwerp voor meer informatie.

In de resterende onderwerpen in dit gedeelte wordt beschreven hoe deze functies moeten worden gebruikt. Zie '[Procedures voor RMS ...](https://technet.microsoft.com/82032075-f361-438f-a2c4-93ab29ae6cff)' verderop in dit onderwerp voor stapsgewijze instructies.

| ![](images/Cc720290.note(WS.10).gif)Opmerking                                                                                                                                                                                    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| De beheerwebsite van RMS gebruikt pop-upvensters voor de configuratie van sommige functies. Als u pop-upblokkering gebruikt in uw webbrowser, moet u uw browserinstellingen dusdanig configureren dat pop-ups van de beheerwebsite van RMS worden toegestaan. |
