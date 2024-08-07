# John The Ripper

## **What is this?**

<mark style="color:blue;">**John the Ripper (JTR or john)**</mark>** is an essential pentesting tool used to check the strength of passwords and crack encrypted (or hashed) passwords using either brute force or dictionary attacks. It is open-source software initially developed for UNIX-based systems and first released in 1996.**

## Cracking Modes

### <mark style="color:blue;">**Single Crack Mode**</mark>

Is one of the most common John modes used when attempting to crack passwords using a single password list. It is a **brute-force** attack which use single password list, meaning all passwords on the list are tried, one by one, until the correct one is found.

```bash
$ john --format=sha256 hashes_to_crack.txt
```

### <mark style="color:blue;">**Wordlist Mode**</mark>&#x20;

Is used to crack passwords using multiple lists of words. It is a dictionary attack which means it will try all the words in the lists one by one until it finds the right one. It is almost same with **Single Crack Mode**, just uses custom wordlists.

```bash
$ john --wordlist=<wordlist_file> --rules <hash_file>
```

## <mark style="color:blue;">**Incremental Mode**</mark>&#x20;

is an advanced **John** mode used to crack passwords using a character set. It is a **hybrid attack**, which means it will attempt to match the password by trying all possible combinations of characters from the character set.

```bash
$ john --incremental <hash_file>
```

## <mark style="color:blue;">**Cracking Files**</mark>

```bash
$ locate *2john #locate tools to make file crackable
$ pdf2john server_doc.pdf > server_doc.hash
$ john server_doc.hash
$ john --wordlist=<wordlist.txt> server_doc.hash
```
