---
description: Other useful not-so-big tools.
---

# Other

## username-anarchy

[**\[LINK\]**](https://github.com/urbanadventurer/username-anarchy) Tool of generating random credentials  for making a wordlist

```bash
./username-anarchy -i /home/amogus1/names.txt 
```

## linikatz

[**\[LINK\]**](https://github.com/CiscoCXSecurity/linikatz) Just mimikatz analogue for Linux

```bash
./linikatz.sh
```

## pwncat-cs

[**\[LINK\]**](https://github.com/calebstewart/pwncat?tab=readme-ov-file) Other better version of **pwncat**. Here is also [**\[DOCS\]**](https://pwncat.readthedocs.io/en/latest/) which could help you in installing and using

```bash
Listener: pwncat-cs 13.13.13.13 1337
#(To change from pwncat shell to local shell, use Ctrl+D)
```

## CeWL

[**CeWL**](https://www.geeksforgeeks.org/cewl-tool-creating-custom-wordlists-tool-in-kali-linux/) **(pronounced "cool") is a custom word list generator tool that spiders websites to create word lists based on the site's content**

{% code fullWidth="false" %}
```bash
cewl -d 0 -m 5 -w usernames.txt http://MACHINE_IP/team.php --lowercase
```
{% endcode %}

## WPScan

Useful tool for **Wordpress** pentesting.

```bash
wpscan --url http://13.13.13.13 --api-token DUVjyYasikdjflasjhflajds1zb5ampmFuTA4DNXYsf4
wpscan --url http://13.13.13.13 --usernames names.txt --passwords pass.txt
```

## Wormhole

[**\[LINK\]**](https://github.com/magic-wormhole/magic-wormhole) **CMD Tool for secure sending**&#x20;
