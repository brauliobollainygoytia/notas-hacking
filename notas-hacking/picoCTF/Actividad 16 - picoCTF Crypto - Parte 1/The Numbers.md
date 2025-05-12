# The Numbers
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?
The flag is in the format PICOCTF{}

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2025-05-11 14:17:46--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png                           100%[===================================================================================>]  98.36K   484KB/s    in 0.2s    

2025-05-11 14:17:47 (484 KB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ open c           
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ open the_numbers.png 

```
Después de abrir la imagen, vemos unos números que están codificados y se usa cyberchef para descodificarlos
```
picoctfthenumbersmason
```

### Referencias
https://youtu.be/I95FPcH27j0?si=C1VwinWlg13W8G4a