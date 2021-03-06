---
TOCTitle: Accountcertificeringsservice van RMS
Title: Accountcertificeringsservice van RMS
ms:assetid: 'fb294969-850e-44b4-8f6a-ca5d5cec1bf1'
ms:contentKeyID: 18114239
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc747802(v=WS.10)'
---

Accountcertificeringsservice van RMS
====================================

De accountcertificeringsservice wordt alleen uitgevoerd in het basiscluster. Met de accountcertificeringsservice worden rechtenaccountcertificaten gemaakt waarmee gebruikersaccounts worden gekoppeld aan bepaalde computers. Met een rechtenaccountcertificaat kan een gebruiker op een bepaalde computer door rechten beveiligde inhoud uitgeven of gebruiken.

Het toepassingsbestand voor de accountcertificeringsservice, Certification.asmx, bevindt zich in de virtuele map Certification in IIS.

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
<tr class="even">
<td style="border:1px solid black;">Gebruikers</td>
<td style="border:1px solid black;">Lezen en uitvoeren</td>
</tr>
</tbody>
</table>
