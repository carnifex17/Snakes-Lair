---
description: Tools, command for exploring and hacking network
---

# Network Hacking

## Ping Scan

```bash
for i in {1..255} ;do (ping -c 1 13.13.13.$i | grep "bytes from"|cut -d ' ' -f4|tr -d ':' &);done
```
