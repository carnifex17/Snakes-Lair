# IP / Subnetting

## IP

<mark style="color:red;">**IP or Internet Protocol is Network OSI layer**</mark> <mark style="color:purple;">**protocol**</mark>, which is used for identifying devices in the Internet. For this it uses IP addresses. Computer gets it's IP address from software and obtained automatically from a **DHCP** server. IP addresses, whether <mark style="color:purple;">**dynamic**</mark> or <mark style="color:purple;">**static**</mark>, are assigned to a <mark style="color:red;">**Network Interface Controller (NIC)**</mark>, also known as a <mark style="color:yellow;">**Network Adapter**</mark>. A system can have multiple **NICs** (both <mark style="color:purple;">**physical**</mark> and <mark style="color:purple;">**virtual**</mark>), allowing it to connect to different networks with multiple IP addresses. Identifying pivoting opportunities often depends on the IPs assigned to compromised hosts, as they reveal the networks those hosts can access.

## Subnet

There are billions of devices, so to communicate fast and easy with each of it, IP connects firstly not to devices itself, but to <mark style="color:red;">**subnet**</mark>, in which this device is located. This is called <mark style="color:red;">**Scaling**</mark>. Also IP address is <mark style="color:yellow;">**32 bit number**</mark>, where every <mark style="color:yellow;">**8 bit**</mark> is called octet

<mark style="color:red;">**Subnet**</mark> - is the set of computers, which older part of IP address is same:

* <mark style="color:green;">**`312.245.10.1`**</mark>
* <mark style="color:green;">**`312.245.10.2`**</mark>
* <mark style="color:green;">**`312.245.10.3`**</mark>

### Subnet Mask

<mark style="color:red;">**Subnet mask**</mark> is <mark style="color:yellow;">**32-bit**</mark> <mark style="color:purple;">**number**</mark>, which shows us, where in IP address number of network, and where is host. Previously, **Subnet Classes** were used to classify subnets, but this scheme is outdated, so they started using <mark style="color:yellow;">**CIDR**</mark>, which means <mark style="color:yellow;">**Classless Inter-Domain Routing**</mark>

Mask structure:

* **1** in position, specifying net number
* **0** in position, specifying host number

| Explanation                                          | Number                                                                                                       |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| <mark style="color:green;">**`IP(Decimal):`**</mark> | **213.180.193.3**                                                                                            |
| <mark style="color:green;">**`IP:`**</mark>          | <mark style="color:blue;">**11010101.10110100.11000001.00000011**</mark>                                     |
| <mark style="color:green;">**`Mask:`**</mark>        | <mark style="color:red;">**11111111.11111111.11111111.00000000**</mark>                                      |
| <mark style="color:green;">**`Subnet:`**</mark>      | <mark style="color:blue;">**11010101.10110100.11000001**</mark><mark style="color:red;">**.00000000**</mark> |

Subnet mask could be shown with 2 types: decimal and prefix

* <mark style="color:purple;">**Decimal**</mark>: <mark style="color:green;">**255.255.255.0**</mark>
* <mark style="color:purple;">**Prefix**</mark>: <mark style="color:green;">**/24**</mark>. Prefix 24 means 24 bits of subnet address in IP address.

The subnet mask does not have to end on an octet boundary

| Explanation                                              | Number                              |
| -------------------------------------------------------- | ----------------------------------- |
| <mark style="color:green;">**`IP(Decimal):`**</mark>     | 213.180.193.3 /20                   |
| <mark style="color:green;">**`IP:`**</mark>              | 11010101.10110100.11000001.00000011 |
| <mark style="color:green;">**`Mask:`**</mark>            | 11111111.11111111.11110000.00000000 |
| <mark style="color:green;">**`Subnet:`**</mark>          | 11010101.10110100.11000000.00000000 |
| <mark style="color:green;">**`Subnet(Decimal):`**</mark> | 213.180.192.0                       |
| <mark style="color:green;">**`Host(Decimal):`**</mark>   | 0.0.1.3                             |

So algorithm is that you should replace all **one's** in IP with **zero's** in mask at the same position.
