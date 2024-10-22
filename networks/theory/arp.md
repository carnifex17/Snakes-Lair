# ARP

## About

**The acronym `ARP` stands for `Address Resolution Protocol` which is one of the most important protocols of the Data link layer in the `OSI` model. It is responsible to find the hardware address of a host from a known `IP` address. So as I get we use ARP when we need to send some info on 2 level of `OSI`, which requires `MAC` address. Every machine has it's own `ARP` cache, where is table like IP-MAC data. So when we need to send some data on `Data Link` level, we broadcast request to entire network like "Hey, who is 10.10.10.10, I want to find his MAC". And if we found it address, it will tell us back with "Hi, you looking for 10.10.10.10? It's me, here's my MAC".**

## ARP Spoofing & ARP DOS

### Bettercap

**Bettercap is a powerful, modular, and flexible open-source tool designed for network penetration testing. It is primarily used for network discovery, man-in-the-middle attacks, and other security assessments. Bettercap is written in Go and comes with a variety of features that make it a valuable tool for security professionals and ethical hackers. Here are some key aspects that make Bettercap useful:**

***

**Example**

_Ban the address 192.168.1.6 from the network:_

```linux
> set arp.spoof.targets 192.168.1.6; arp.ban on
```

_Spoof 192.168.1.2, 192.168.1.3 and 192.168.1.4:_

```linux
> set arp.spoof.targets 192.168.1.2-4; arp.spoof on
```

**After spoofing or poisoning we could look or change traffic with wireshark**
