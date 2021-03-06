---
TOCTitle: Service van RMS voor uit bedrijf nemen
Title: Service van RMS voor uit bedrijf nemen
ms:assetid: '97677e3b-bc83-47ec-b6db-d326cd94566c'
ms:contentKeyID: 18114088
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747695(v=WS.10)'
---

Service van RMS voor uit bedrijf nemen
======================================

De service Uit bedrijf nemen is een aangepaste webservice die wordt geïnstalleerd met het installatieprogramma van RMS. Het wordt uitgevoerd in het basiscluster en in clusters die alleen voor licentieverlening worden gebruikt. Wanneer u deze service inschakelt, worden de andere RMS-webservices op de server uitgeschakeld.

Met deze service wordt de inhoudssleutel in de uitgiftelicentie van door rechten beveiligde inhoud gedecodeerd en aan clients geleverd die een licentie aanvragen. Zo kan de inhoud zonder RMS-beveiliging worden opgeslagen. Met de service voor uit bedrijf nemen worden alle ingediende clientaanvragen vastgelegd, naar de service van de logboekregistratie-listener verstuurd en in de logboekdatabase opgenomen.

U kunt de service Uit bedrijf nemen inschakelen via de pagina **Beveiligingsinstellingen** van de beheerwebsite. Als u deze service inschakelt, kunt u de standaardconfiguratie van RMS niet meer herstellen.

Hebt u deze service ingeschakeld, dan moet u de DACL in het bestand decommission.asmx zodanig instellen, dat deze toegankelijk is voor de gebruikers in uw onderneming die deze server hebben gebruikt om hun inhoud te beveiligen met een licentie. U moet tevens de RMS-servicegroep met lees- en uitvoeringsrechten aan de DACL toevoegen, zodat RMS deze bewerking kan beheren. Wanneer de beveiliging op alle door deze server uitgegeven inhoud is opgeheven, maakt u een back-up van de persoonlijke-sleutelgegevens en verwijdert u RMS van de server.

In de volgende tabel wordt de standaard-ACL (Access Control List) van deze service weergegeven:

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Gebruiker of groep</th>
<th style="border:1px solid black;" >Standaardmachtiging</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">SYSTEM</td>
<td style="border:1px solid black;">Volledig beheer</td>
</tr>
</tbody>
</table>
