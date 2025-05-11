# flags are stepic
A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message
Additional details will be available after launching your challenge instance.
In the country that doesn't exist, the flag persists

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget http://standard-pizzas.picoctf.net:64658/flags/upz.png
--2025-05-11 13:55:52--  http://standard-pizzas.picoctf.net:64658/flags/upz.png
Resolving standard-pizzas.picoctf.net (standard-pizzas.picoctf.net)... 3.22.195.189
Connecting to standard-pizzas.picoctf.net (standard-pizzas.picoctf.net)|3.22.195.189|:64658... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1788398 (1.7M) [image/png]
Saving to: ‘upz.png’

upz.png                                   100%[===================================================================================>]   1.71M  1.84MB/s    in 0.9s    

2025-05-11 13:55:53 (1.84 MB/s) - ‘upz.png’ saved [1788398/1788398]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls -la 
total 1756
drwxrwxr-x 2 kali kali    4096 May 11 13:55 .
drwxrwxr-x 7 kali kali    4096 May  9 20:36 ..
-rw-rw-r-- 1 kali kali 1788398 Mar  5 21:58 upz.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ stepic -i upz.png -d   
/usr/lib/python3/dist-packages/PIL/Image.py:3368: DecompressionBombWarning: Image size (150658990 pixels) exceeds limit of 89478485 pixels, could be decompression bomb DOS attack.
  warnings.warn(
picoCTF{fl4g_h45_fl4g6f5548ea}  
```

### Referencias
https://youtu.be/EXuKrStFsQo?si=aiAHLjTjvsP4mRIs