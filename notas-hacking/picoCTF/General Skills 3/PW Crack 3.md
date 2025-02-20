# PW Crack 3
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
To exit `bvi` type `:q` and press enter.
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Con la terminal de kali linux, python y visual studio code
```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ ls -la
total 36
drwxrwxr-x 2 kali kali 4096 Feb 20 14:40 .
drwxrwxr-x 5 kali kali 4096 Feb 20 14:40 ..
-rw-rw-r-- 1 kali kali   30 Feb 20 14:01 level1.flag.txt.enc
-rw-rw-r-- 1 kali kali  876 Feb 20 14:01 level1.py
-rw-rw-r-- 1 kali kali   31 Feb 20 14:22 level2.flag.txt.enc
-rw-rw-r-- 1 kali kali  914 Feb 20 14:22 level2.py
-rw-rw-r-- 1 kali kali   31 Feb 20 14:34 level3.flag.txt.enc
-rw-rw-r-- 1 kali kali   16 Feb 20 14:34 level3.hash.bin
-rw-rw-r-- 1 kali kali 1405 Feb 20 14:44 level3.py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ cat level3.py 
import hashlib

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

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]

def level_3_pw_check():
    #user_pw = input("Please enter correct password for flag: ")

    for user_pw in pos_pw_list:
        user_pw_hash = hash_pw(user_pw)
        
        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python level3.py 
That password is incorrect
That password is incorrect
That password is incorrect
That password is incorrect
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}

```
