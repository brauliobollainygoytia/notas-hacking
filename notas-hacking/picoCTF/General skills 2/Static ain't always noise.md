# Static ain't always noise
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? This [BASH script](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) might help!

## Solución
Con la terminal de kali linux

```
kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
--2025-02-18 12:28:52--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: ‘static’

static                                    100%[===================================================================================>]   8.18K  --.-KB/s    in 0s      

2025-02-18 12:28:53 (131 MB/s) - ‘static’ saved [8376/8376]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh
--2025-02-18 12:29:32--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: ‘ltdis.sh’

ltdis.sh                                  100%[===================================================================================>]     785  --.-KB/s    in 0s      

2025-02-18 12:29:32 (20.1 MB/s) - ‘ltdis.sh’ saved [785/785]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ chmod +x static
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ ./static 
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ bash ltdis.sh 

Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ chmod +x ltdis.sh 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ cat static.ltdis.strings.txt | grep picoCTF
   1020 picoCTF{d15a5m_t34s3r_f5aeda17}

```