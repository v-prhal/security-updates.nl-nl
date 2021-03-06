---
TOCTitle: Update Status Terminology
Title: Update Status Terminology
ms:assetid: '242975b0-8ae1-4763-b562-198fc1651149'
ms:contentKeyID: 18126749
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720463(v=WS.10)'
---

Update Status Terminology
=========================

You can access update status from various locations in the WSUS console. The following table defines each possible status that can be reported by WSUS for an update. Typically, WSUS presents update status for a particular computer (for example, the status of an update on one computer) or computer group (for example, status for the five computers in Computer Group X on which the update has been installed).

### Update Status Definitions

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Status</th>
<th style="border:1px solid black;" >Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Installed</td>
<td style="border:1px solid black;">The update was installed on the computer.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Needed</td>
<td style="border:1px solid black;">This is the positive result of a Detect only approval. When referring to the status of one computer, Needed means the update is compliant with (and should be installed on) the computer. When referring to status for a computer group, the <strong>Needed</strong> column displays the number of computers in the group with which the update is compliant. Additionally, a positive Needed result means, technically, that as of the last time client computers made contact with the WSUS server, the update was determined to be compliant, but has not been installed. Therefore, it is possible that any of the following could be true when the status for an update is Needed:
You have approved the update for installation but the client computers have not yet contacted the WSUS server since you made this change.
You have not yet approved the update for installation, although the Detect only action has been performed.
The update has already been downloaded and installed, but the client computer has not contacted the WSUS server since the update was installed.
The update has already been downloaded and installed but the update requires that the client computer be restarted before changes go into effect, and the client computer has not yet been restarted.
The update has been downloaded to the computer but not installed.
The update has been neither downloaded nor installed on the computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Not needed</td>
<td style="border:1px solid black;">This is the negative result of a Detect only approval. When referring to the status of one computer, Not needed means the update is not compliant with or required by that computer. When referring to the status for a computer group, the <strong>Not needed</strong> column displays the number of computers in the group for which the update is not compliant or required.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unknown</td>
<td style="border:1px solid black;">Typically, this means that since the time that the update was synchronized to the WSUS server, the computer has not contacted the WSUS server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Failed</td>
<td style="border:1px solid black;">An error occurred when either a detection or an installation was attempted on the computer for the update.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Last contacted</td>
<td style="border:1px solid black;">This is the date on which the computer last contacted the WSUS server.</td>
</tr>
</tbody>
</table>
