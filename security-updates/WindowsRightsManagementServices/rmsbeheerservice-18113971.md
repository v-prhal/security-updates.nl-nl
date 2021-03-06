---
TOCTitle: 'RMS-beheerservice'
Title: 'RMS-beheerservice'
ms:assetid: '4bd3e142-f0f6-40e9-a160-deab28ce5b88'
ms:contentKeyID: 18113971
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747560(v=WS.10)'
---

RMS-beheerservice
=================

De beheerservice wordt uitgevoerd in het RMS-basiscluster. Daarnaast wordt deze service uitgevoerd in elk cluster dat alleen voor licentieverlening wordt gebruikt. Met de beheerservice kunt u RMS beheren. De beheerwebsite maakt deel uit van deze service.

Het toepassingsbestand voor de beheerservice, Default.aspx, bevindt zich in de virtuele map Admin (*RMS-website*\\\_wmcs\\Admin). *RMS\_Web\_site* wordt vervangen door de naam van de website waarop u RMS hebt ingericht.

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
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Volledig beheer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RMS-servicegroep</td>
<td style="border:1px solid black;">Lezen en uitvoeren</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SYSTEM</td>
<td style="border:1px solid black;">Volledig beheer</td>
</tr>
</tbody>
</table>
