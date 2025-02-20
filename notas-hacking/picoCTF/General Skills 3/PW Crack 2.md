# PW Crack 2
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.
Does that encoding look familiar?
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Con la terminal de kali linux y python
```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ ls -la
total 24
drwxrwxr-x 2 kali kali 4096 Feb 20 14:25 .
drwxrwxr-x 5 kali kali 4096 Feb 20 14:25 ..
-rw-rw-r-- 1 kali kali   30 Feb 20 14:01 level1.flag.txt.enc
-rw-rw-r-- 1 kali kali  876 Feb 20 14:01 level1.py
-rw-rw-r-- 1 kali kali   31 Feb 20 14:22 level2.flag.txt.enc
-rw-rw-r-- 1 kali kali  914 Feb 20 14:22 level2.py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ cat level2.py 
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python          
Python 3.12.8 (main, Feb  1 2025, 21:32:22) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x64)
'd'
>>> chr(0x65)
'e'
>>> chr(0x37)
'7'
>>> chr(0x36)
'6'
>>> 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}

```