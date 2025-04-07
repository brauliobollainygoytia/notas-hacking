# WhitePages
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!

## Solución
Con la terminal de Kali linux, python y pwntools
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt'
--2025-04-06 14:54:10--  https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2964 (2.9K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt                            100%[==================================================================================>]   2.89K  --.-KB/s    in 0s      

2025-04-06 14:54:11 (69.2 MB/s) - ‘whitepages.txt’ saved [2964/2964]

                                                                                                                                                                     
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ file whitepages.txt 
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1376), with no line terminators
──(pwntools-venv)─(kali㉿kali)-[~/Documents/srss/forensic]
└─$ nano exp.py

#Codigo de python
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83', b'0')
data = data.replace(b'\x20', b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)

┌──(pwntools-venv)─(kali㉿kali)-[~/Documents/srss/forensic]
└─$ python exp.py
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}\n\t\t'


```