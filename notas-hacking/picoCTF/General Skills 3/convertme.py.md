# convertme.py
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/23/convertme.py)
Look up a decimal to binary number conversion app on the web or use your computer's calculator!
The `str_xor` function does not need to be reverse engineered for this challenge.
If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución
Con la terminal de kali linux y python
```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ ls -la
total 12
drwxrwxr-x 2 kali kali 4096 Feb 20 13:23 .
drwxrwxr-x 5 kali kali 4096 Feb 20 13:23 ..
-rw-rw-r-- 1 kali kali 1189 Feb 20 13:23 convertme.py
-rw-rw-r-- 1 kali kali    0 Feb 18 12:30 .ltdis.x86_64.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills3]
└─$ python convertme.py        
If 58 is in decimal base, what is it in binary base?
Answer: 111010
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}

┌──(kali㉿kali)-[~]
└─$ python  
Python 3.12.8 (main, Feb  1 2025, 21:32:22) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(58)[2:]
'111010'
>>> 

```
