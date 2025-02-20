# fixme1.py
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/25/fixme1.py)
Indentation is very meaningful in Python
To view the file in the webshell, do: `$ nano fixme1.py`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Con la terminal de kali linux y nano
```
──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ ls -la
total 16
drwxrwxr-x 2 kali kali 4096 Feb 20 13:42 .
drwxrwxr-x 5 kali kali 4096 Feb 20 13:42 ..
-rw-rw-r-- 1 kali kali 1189 Feb 20 13:23 convertme.py
-rw-rw-r-- 1 kali kali  837 Feb 20 13:41 fixme1.py
-rw-rw-r-- 1 kali kali    0 Feb 18 12:30 .ltdis.x86_64.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ nano fixme1.py                         
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python fixme1.py   
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) >

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)
```
