# Mind your Ps and Qs
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values)
Bits are expensive, I used only a little bit over 100 to save money

## Solución
Con la terminal de Kali Linux y python
```
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ wget https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values    
--2025-05-23 10:39:03--  https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 205 [application/octet-stream]
Saving to: ‘values’

values                                    100%[===================================================================================>]     205  --.-KB/s    in 0s      

2025-05-23 10:39:03 (169 MB/s) - ‘values’ saved [205/205]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ cat values              
Decrypt my super sick RSA:
c: 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n: 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e: 65537

┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ python        
Python 3.12.8 (main, Feb  1 2025, 21:32:22) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 62324783949134119159408816513334912534343517300880137691662780895409992760262021
>>> n = 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
>>> e = 65537
>>> p = 1899107986527483535344517113948531328331
>>> q = 674357869540600933870145899564746495319033
>>> tn = (p - 1) * (q - 1)
>>> d = pow(e, -1, tn)
>>> m = pow (c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639555654677400177227645
>>> bytes.fromhex(hex(m)[2:])
b'picoCTF{sma11_N_n0_g0od_05012767}'

```