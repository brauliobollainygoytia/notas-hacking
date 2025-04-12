If you want to hash with the best, beat this test!
You can use a commandline tool or web app to hash text
Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución
Con la terminal de kali linux
```
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 64366
Please md5 hash the text between quotes, excluding the quotes: 'Michele Pfeifer'
Answer: 
5aa67b1e7680114db194886efc6967c2
5aa67b1e7680114db194886efc6967c2
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'apples'
Answer: 
daeccf0ad3c1fc8c8015205c332f5b42
daeccf0ad3c1fc8c8015205c332f5b42
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'coconuts'
Answer: 
78d1999482f432e9c229269151140542
78d1999482f432e9c229269151140542
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_3eb82b73}

┌──(kali㉿kali)-[~]
└─$ echo -n "Michele Pfeifer" | md5sum
5aa67b1e7680114db194886efc6967c2  -
                                                                                 
┌──(kali㉿kali)-[~]
└─$ echo -n "apples" | md5sum
daeccf0ad3c1fc8c8015205c332f5b42  -
                                                                                 
┌──(kali㉿kali)-[~]
└─$ echo -n "coconuts" | md5sum
78d1999482f432e9c229269151140542  -
                                                                                 
┌──(kali㉿kali)-[~]
└─$ echo -n "coconuts" | md5sum
78d1999482f432e9c229269151140542  -

```
