# St3g0
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)
We know the end sequence of the message will be `$t3g0`.
## Solución
Con Kali Linux, python y image-stego-tool del repo https://github.com/djrobin17/image-stego-tool.git

```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ git clone https://github.com/djrobin17/image-stego-tool.git                                                                                                      
Cloning into 'image-stego-tool'...
remote: Enumerating objects: 32, done.
remote: Counting objects: 100% (32/32), done.
remote: Compressing objects: 100% (29/29), done.
remote: Total 32 (delta 10), reused 6 (delta 2), pack-reused 0 (from 0)
Receiving objects: 100% (32/32), 27.92 KiB | 1.99 MiB/s, done.
Resolving deltas: 100% (10/10), done.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://artifacts.picoctf.net/c/216/pico.flag.png                          
--2025-05-09 20:53:00--  https://artifacts.picoctf.net/c/216/pico.flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13441 (13K) [application/octet-stream]
Saving to: ‘pico.flag.png’

pico.flag.png                             100%[===================================================================================>]  13.13K  --.-KB/s    in 0.02s   

2025-05-09 20:53:01 (832 KB/s) - ‘pico.flag.png’ saved [13441/13441]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls    
image-stego-tool  pico.flag.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ cd image-stego-tool 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic/image-stego-tool]
└─$ ls
README.md  stego.py  stego-start.png

┌──(kali㉿kali)-[~/Documents/srss/forensic/image-stego-tool]
└─$ python stego.py
--Welcome to $t3g0--
1: Encode
2: Decode
2
Enter Source Image Path
../pico.flag.png
Enter Password
$t3g0
Decoding...
Hidden Message: picoCTF{7h3r3_15_n0_5p00n_a1062667}

```