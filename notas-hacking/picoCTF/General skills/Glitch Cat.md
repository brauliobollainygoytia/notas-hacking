Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.
ASCII is one of the most common encodings used in programming
We know that the glitch output is valid Python, somehow!
Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 50094`

## Solucion
Con la terminal de kali linux y python
```
┌──(kali㉿kali)-[~]
└─$ nc saturn.picoctf.net 50094
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
                                                                                                                                                                       
┌──(kali㉿kali)-[~]
└─$ python                     
Python 3.12.8 (main, Feb  1 2025, 21:32:22) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}')
picoCTF{gl17ch_m3_n07_a4392d2e}

```
