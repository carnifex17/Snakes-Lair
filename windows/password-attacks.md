# Password Attacks

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
