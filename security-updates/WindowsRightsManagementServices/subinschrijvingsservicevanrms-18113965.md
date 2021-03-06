---
TOCTitle: Subinschrijvingsservice van RMS
Title: Subinschrijvingsservice van RMS
ms:assetid: '6b05e71c-5e7d-467c-9e13-35ac14d3718a'
ms:contentKeyID: 18113965
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720289(v=WS.10)'
---

Subinschrijvingsservice van RMS
===============================

De subinschrijvingsservice wordt uitsluitend uitgevoerd in het RMS-basiscluster. Met deze service wordt gereageerd op aanvragen voor serverlicentiecertificaten die tijdens het inrichtingsproces via servers van licentieverleningsclusters worden verstuurd.

Het toepassingsbestand van de subinschrijvingsservice, SubEnrollService.asmx, staat in de virtuele map *RMS\_website*\\\_wmcs\\Certification\\, waarbij *RMS\_website* wordt vervangen door de naam van de website waarop u RMS hebt ingericht.

De toegang tot deze service is standaard beperkt tot de lokale systeemaccount. Om een onderliggende server in te richten en in te schrijven in een cluster dat alleen voor licentieverlening wordt gebruikt, moet de gebruikersaccount van de beheerder met volledige bevoegdheden voor de licentieserver worden toegevoegd aan de DACL (Discretionary Access Control List) van SubEnrollService.asmx.

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
