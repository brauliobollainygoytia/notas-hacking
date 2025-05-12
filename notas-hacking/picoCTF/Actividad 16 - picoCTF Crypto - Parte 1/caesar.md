# caesar
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext     
--2025-05-11 14:49:59--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 35 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext                                100%[===================================================================================>]      35  --.-KB/s    in 0s      

2025-05-11 14:49:59 (61.0 MB/s) - ‘ciphertext’ saved [35/35]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ cat ciphertext 
picoCTF{ynkooejcpdanqxeykjrbdofgkq}     
```
Usando CyberChef para decodificar la bandera 
```
crossingtherubiconvfhsjkou
```

### Referencias
https://youtu.be/2x4bhYsKtds?si=oDJke9bEbda-_5pW
