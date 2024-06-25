# Theory

## What is Active Directory

<mark style="color:red;">**Active Directory (AD)**</mark> is a directory service developed by **Microsoft** for Windows domain networks. It is included in most Windows Server operating systems as a set of processes and services. Active Directory plays a crucial role in managing the identities and relationships that make up network environments. Active Directory hacking is very complex topic

### Key Concepts of Active Directory

* <mark style="color:red;">**Domain**</mark><mark style="color:red;">:</mark> The basic unit of structure in an Active Directory network. A domain is a collection of objects such as users, groups, and computers that are managed centrally.
* <mark style="color:red;">**Forest**</mark><mark style="color:red;">:</mark> A collection of one or more domain trees. Forests enable global policies and trust relationships across multiple domains.
* <mark style="color:red;">**Tree**</mark><mark style="color:red;">:</mark> A hierarchy of domains in Active Directory that share a contiguous namespace.
* <mark style="color:red;">**Organizational Unit (OU)**</mark><mark style="color:red;">:</mark> A container within a domain that can hold users, groups, computers, and other OUs. OUs allow the organization of objects within a domain and the application of policies at a granular level.
* <mark style="color:red;">**Global Catalog**</mark><mark style="color:red;">:</mark> A distributed data repository that contains a searchable, partial representation of every object in every domain within a forest. It is used to improve query performance and facilitate logon processes across domains.

After Windows system became part of the domain, it's interaction with SAM is over, they've broke up and it's new boyfriend is Domain Controller. And all questions about checking password would now be sent to Domain Controller, not SAM.  But in some ways system could come over to SAM if specify the `hostname` of the device proceeded by the `username` like <mark style="color:blue;">**WS01/nameofuser**</mark><mark style="color:green;">**.**</mark>&#x20;

## NTDS.DIT

<mark style="color:red;">**NTDS.DIT**</mark> stands for <mark style="color:red;">**New Technology Directory Services Directory Information Tree**</mark>. It is main database file within Microsoft’s <mark style="color:red;">**Active Directory Domain Services**</mark> (AD DS). **NTDS.DIT** stores and organizes all the information related to objects in the domain, including **users**, **groups**, **computers**, and more. It acts as the backbone of Active Directory, housing critical data such as **user account details**, **passwords**, **group memberships**, and other **object attributes**.

***

## Important Files Location

* <mark style="color:green;">**%systemroot%/ntds**</mark>** **_**- Location of NTDS.dir file**_

