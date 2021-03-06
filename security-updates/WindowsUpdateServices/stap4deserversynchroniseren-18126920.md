---
TOCTitle: 'Stap 4: De server synchroniseren'
Title: 'Stap 4: De server synchroniseren'
ms:assetid: 'a5514e46-a50b-46a6-9e5b-33c87c5b7cef'
ms:contentKeyID: 18126920
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc708523(v=WS.10)'
---

Stap 4: De server synchroniseren
================================

Nadat u de netwerkverbinding hebt geconfigureerd, kunt u updates ophalen. WSUS is standaard geconfigureerd om essentiële updates en beveiligingsupdates voor alle Microsoft-producten te downloaden. Als u deze updates wilt ophalen, moet u de WSUS-server *synchroniseren*.

Dit houdt in dat de WSUS-server verbinding moet maken met Microsoft Update. Nadat de verbinding tot stand is gebracht, stelt WSUS vast of er nieuwe updates beschikbaar zijn geworden sinds de vorige keer dat u de server hebt gesynchroniseerd. Omdat dit de eerste keer is dat u de WSUS-server met Windows Update synchroniseert, zijn alle updates beschikbaar en gereed om door u voor installatie te worden goedgekeurd.

| ![](images/Cc708523.note(WS.10).gif)Opmerking                                                                                                                                                                                                                                                              |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| In dit document wordt beschreven hoe u de WSUS-server synchroniseert met de standaardinstellingen, maar WSUS heeft ook opties waarmee u het bandbreedtegebruik tot een minimum kunt beperken tijdens het synchroniseren. Raadpleeg het Engelstalige document 'Deploying Microsoft Windows Server Update Services' voor meer informatie. |

**De WSUS-server synchroniseren**
1.  Klik op de werkbalk van de WSUS-console op **Opties** en klik vervolgens op **Opties voor synchronisatie**.

2.  Klik onder **Taken** op **Nu synchroniseren**.

Nadat het synchroniseren is voltooid, klikt u op de **Updates** op werkbalk van de WSUS-console om de lijst met updates weer te geven.
