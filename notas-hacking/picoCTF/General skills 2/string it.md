# string it
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?
[strings](https://linux.die.net/man/1/strings)

## Solución
Con la terminal de kali linux

```
                                                                                                                                                                     
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ wget https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
--2025-02-18 12:18:15--  https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: ‘strings’

strings                                   100%[===================================================================================>] 757.84K   701KB/s    in 1.1s    

2025-02-18 12:18:17 (701 KB/s) - ‘strings’ saved [776032/776032]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_827aee91}

```