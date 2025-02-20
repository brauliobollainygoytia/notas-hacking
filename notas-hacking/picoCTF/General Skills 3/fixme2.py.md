# fixme2.py
Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/6/fixme2.py)
Are equality and assignment the same symbol?
To view the file in the webshell, do: `$ nano fixme2.py`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Con la terminal de kali linux y nano

```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ ls -la
total 20
drwxrwxr-x 2 kali kali 4096 Feb 20 13:49 .
drwxrwxr-x 5 kali kali 4096 Feb 20 13:49 ..
-rw-rw-r-- 1 kali kali 1189 Feb 20 13:23 convertme.py
-rw-rw-r-- 1 kali kali  835 Feb 20 13:43 fixme1.py
-rw-rw-r-- 1 kali kali 1029 Feb 20 13:49 fixme2.py
-rw-rw-r-- 1 kali kali    0 Feb 18 12:30 .ltdis.x86_64.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python fixme2.py 
  File "/home/kali/Documents/srss/GeneralSkills3/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ nano fixme2.py 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) >

  
flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)

```