---
TOCTitle: Managing Computer Groups
Title: Managing Computer Groups
ms:assetid: '14fbb1ef-b9b8-4c9e-a42a-a7237948251a'
ms:contentKeyID: 18126740
ms:mtpsurl: 'https://technet.microsoft.com/nl-nl/library/Cc720450(v=WS.10)'
---

Managing Computer Groups
========================

WSUS enables you to target updates to groups of client computers. This capability can help you ensure that specific computers get the right updates at the most convenient times on an ongoing basis. For example, if all computers in one department of your organization have a specific configuration (such as all computers in the Accounting team), you can determine what updates those computers get, at what time, and then use WSUS reporting features to evaluate the success of update activity for that computer group.

By default, each computer is already assigned to the All Computers group. Computers will also be assigned to the Unassigned Computers group until you assign them to another group. Regardless of the group you assign a computer to, it will also remain in the All Computers group. A computer can be in only one other group in addition to the All Computers group.

You can assign computers to computer groups by using one of two methods, *server-side* or *client-side targeting*, depending on whether or not you want to automate the process. With server-side targeting, you use the **Move the selected computer** task on the **Computers** page to move one or more client computers to one computer group at a time. With client-side targeting, you use Group Policy or edit the registry settings on client computers to enable those computers to automatically add themselves into the computer groups. You must specify which method you will use by selecting one of the two options on the **Computers Options** page.

| ![](images/Cc720450.note(WS.10).gif)Opmerking                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| If your WSUS server is running in replica mode, you will not be able to create computer groups on that server, you will only inherit the computer groups created on the administration server from which your server inherits its settings. For more information about replica mode, see [Running in Replica Mode](https://technet.microsoft.com/d143c886-30b6-4034-80a2-182171ac8f8b). |

Server-side Targeting
---------------------

With server-side targeting, you use the WSUS console to both create groups and then assign computers to the groups. Server-side targeting is an excellent option if you do not have many client computers to update and you want to move client computers into computer groups manually.

To enable server-side targeting on your WSUS server, click the **Use the Move computers task in Windows Server Update Services** option on the **Computers Options** page.

Client-side Targeting
---------------------

With client-side targeting, you enable client-computers to add themselves to the computer groups you create in the WSUS console. You can enable client-side targeting through Group Policy (in an Active Directory network environment) or by editing registry entries (in a non-Active Directory network environment) for the client computers. When the client computers connect to the WSUS server, they will add themselves into the correct computer group. Client-side targeting is an excellent option if you have many client computers and want to automate the process of assigning them to computer groups.

To enable client-side targeting on your WSUS server, click the **Use Group Policy or registry settings on client computers** option on the **Computers Options** page.

**To specify the method for assigning computers to groups**
1.  On the WSUS console toolbar, click **Options**, and then click **Computer Options**.

2.  In **Computer Options**, do one of the following:

    -   If you want to create groups and assign computers through the WSUS console (server-side targeting), click **Use the Move computers task in Windows Server Update Services**.
    -   If you want to create groups and assign computers by using Group Policy or by editing registry settings on the client computer (client-side targeting), click **Use Group Policy or registry settings on computers**.

3.  Under **Tasks**, click **Save settings**, and then click **OK**.

#### Managing Computer Groups on Your WSUS Server

Regardless of the method you use to assign client computers to computer groups, you must also create the computer groups in the WSUS console. In you use the client-side targeting method, you must create the computer groups in the WSUS console before your client computers can add themselves to them.

**To create a computer group in the WSUS console**
1.  On the WSUS console toolbar, click **Computers**.

2.  Under **Tasks**, click **Create a computer group**.

3.  In **Group name**, type a name for your new computer group, and then click **OK**.

**To remove a computer group**
1.  On the WSUS console toolbar, click **Computers**.

2.  In **Groups**, click the computer group you want to remove.

3.  Under **Tasks**, click **Delete the selected group**, and then click **OK**.

| ![](images/Cc720450.note(WS.10).gif)Opmerking                                                                                                                                                                                                                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| You cannot remove the **Unassigned Computers** or **All Computers** group. Every client computer remains a member of the **All Computers** group in addition to any group you assign it to. Client computers are members of the **Unassigned Computers** group only until you assign them to a computer group. |
