---
TOCTitle: 'Stap 7: Updates goedkeuren en implementeren in WSUS 3.0'
Title: 'Stap 7: Updates goedkeuren en implementeren in WSUS 3.0'
ms:assetid: '88fac442-a9d3-4e74-92f6-3822b7237af1'
ms:contentKeyID: 18126929
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc708475(v=WS.10)'
---

Stap 7: Updates goedkeuren en implementeren in WSUS 3.0
=======================================================

In deze stap keurt u een update goed voor alle testclientcomputers in de testgroep. Computers in de groep zullen zich in de komende 24 uur melden bij de WSUS-server. Na deze periode kunt u de rapportfunctie van WSUS gebruiken om na te gaan of de update op de computers is geïnstalleerd. Als uit de test blijkt dat de update geen problemen oplevert, kunt u dezelfde updates goedkeuren voor de rest van de computers in uw organisatie.

**Stap 7 omvat de volgende procedures**:

-   Een update goedkeuren en implementeren
-   De status van de update controleren

**Een update goedkeuren en implementeren**
1.  Klik op **Updates** in de WSUS-beheerconsole. Hierdoor wordt een overzicht van updates in de standaardweergaven weergegeven (**Alle updates**, **Essentiële updates**, **Beveiligingsupdates** en **Updates van WSUS**). Gebruik voor deze procedure **Alle updates**.

2.  Selecteer in de lijst met updates de updates die u voor installatie wilt goedkeuren. Informatie over een geselecteerde update is beschikbaar in het onderste deel van het deelvenster Updates. Als u in de lijst meerdere aangrenzende updates wilt selecteren, houdt u **SHIFT** ingedrukt terwijl u op de updates klikt. Als u meerdere updates wilt selecteren die niet aan elkaar grenzen, houdt u **CTRL** ingedrukt terwijl u op de updates klikt.

3.  Klik met de rechtermuisknop op de selectie en klik op **Goedkeuren**. Het dialoogvenster **Updates goedkeuren** wordt weergegeven.

4.  Selecteer een van de groepen (bijvoorbeeld **Test**) en klik op de pijl links daarvan. Er verschijnt een snelmenu met de opties **Goedgekeurd voor installatie**, **Goedgekeurd voor verwijdering**, **Niet goedgekeurd**, **Deadline**, **Zelfde als bovenliggend item** en **Toepassen op onderliggende items**. Klik op **Goedgekeurd voor installatie** en klik op **OK**.

5.  Het venster **Voortgang goedkeuring** wordt nu weergegeven, waarin u de voortgang van de verschillende taken met betrekking tot het goedkeuren van updates kunt volgen. Wanneer de procedure voor goedkeuring is voltooid, klikt u op **Sluiten** om dit venster te sluiten.

| ![](images/Cc708475.note(WS.10).gif)Opmerking                                                                          |
|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Voor het goedkeuren van updates kunt u vele opties instellen. U kunt bijvoorbeeld deadlines instellen of de installatie van updates ongedaan maken. |

Na een periode van 24 uur kunt u de rapportfunctie van WSUS gebruiken om na te gaan of de updates op de computers zijn geïmplementeerd.

**De status van een update controleren**
1.  Klik op **Rapporten** in het linkerdeelvenster van de WSUS-beheerconsole.

2.  Op de pagina **Rapporten** ziet u een aantal gestandaardiseerde rapporten. Klik op het rapport **Overzicht van status van update**. Het venster **Updaterapport** wordt geopend.

3.  Als u de lijst met updates wilt filteren, selecteert u de gewenste criteria (bijvoorbeeld **Updates opnemen in deze categorieën**) en klikt u op **Rapport uitvoeren** op de werkbalk van het venster.

4.  Het deelvenster **Updaterapport** wordt geopend. U kunt de status van afzonderlijke updates controleren door een update te selecteren in het linkerdeelvenster. In de laatste sectie van het deelvenster wordt het statusoverzicht van de update getoond.

5.  U kunt dit rapport opslaan of afdrukken door op het betreffende pictogram op de werkbalk te klikken.

Als de updates zonder problemen op de computers uit de testgroep zijn geïnstalleerd, kunt u dezelfde updates goedkeuren voor de overige computers in uw organisatie.
