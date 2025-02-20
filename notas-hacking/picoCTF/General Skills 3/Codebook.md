# Codebook
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/1/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)
On the webshell, use `ls` to see if both files are in the directory you are in
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Con la terminal de kali linux y python
```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ ls -la         
total 16
drwxrwxr-x 2 kali kali 4096 Feb 20 13:12 .
drwxrwxr-x 5 kali kali 4096 Feb 20 13:12 ..
-rw-rw-r-- 1 kali kali   27 Feb 20 13:08 codebook.txt
-rw-rw-r-- 1 kali kali 1278 Feb 20 13:08 code.py
-rw-rw-r-- 1 kali kali    0 Feb 18 12:30 .ltdis.x86_64.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python code.py codebook.txt 
picoCTF{c0d3b00k_455157_d9aa2df2}

```