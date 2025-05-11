# hideme
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/260/flag.png).

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://artifacts.picoctf.net/c/260/flag.png                        
--2025-05-10 11:08:38--  https://artifacts.picoctf.net/c/260/flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.107, 18.154.144.104, 18.154.144.103, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.107|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43005 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                                  100%[===================================================================================>]  42.00K  --.-KB/s    in 0.04s   

2025-05-10 11:08:38 (1.13 MB/s) - ‘flag.png’ saved [43005/43005]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls    
flag.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2944, uncompressed size: 3095, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls 
flag.png  _flag.png.extracted
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ cd _flag.png.extracted    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic/_flag.png.extracted]
└─$ ls
29  29.zlib  9B3B.zip  secret
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic/_flag.png.extracted]
└─$ cd secret             
                                                                                                                                                                      
┌──(kali㉿kali)-[~/…/srss/forensic/_flag.png.extracted/secret]
└─$ ls
flag.png
┌──(kali㉿kali)-[~/…/srss/forensic/_flag.png.extracted/secret]
└─$ ls
flag.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/…/srss/forensic/_flag.png.extracted/secret]
└─$ eog flag.png
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_ad9f6587}
```