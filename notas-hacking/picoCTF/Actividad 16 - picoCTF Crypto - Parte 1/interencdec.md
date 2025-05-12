# interencdec
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/3/enc_flag).
Engaging in various decoding processes is of utmost importance

## Solución
Con la terminal de Kali Linux y CyberChef
```
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ wget https://artifacts.picoctf.net/c_titan/3/enc_flag                                         
--2025-05-12 11:01:00--  https://artifacts.picoctf.net/c_titan/3/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: ‘enc_flag’

enc_flag                                  100%[===================================================================================>]      73  --.-KB/s    in 0s      

2025-05-12 11:01:00 (105 MB/s) - ‘enc_flag’ saved [73/73]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ ls    
enc_flag
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ cat enc_flag                                                                        
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgya3lNRFJvYTJvMmZRPT0nCg==
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ base64 -d enc_flag 
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ== | base64 -d    
wpjvJAM{jhlzhy_k3jy9wa3k_i204hkj6}

picoCTF{caesar_d3cr9pt3d_b204adc6}
```