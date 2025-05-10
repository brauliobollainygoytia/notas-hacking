# Operation Orchid
Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://artifacts.picoctf.net/c/213/disk.flag.img.gz
--2025-05-09 16:15:11--  https://artifacts.picoctf.net/c/213/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.103, 18.154.144.85, 18.154.144.104, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.103|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360922 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                          100%[===================================================================================>]  42.31M  10.2MB/s    in 4.5s    

2025-05-09 16:15:16 (9.50 MB/s) - ‘disk.flag.img.gz’ saved [44360922/44360922]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ gzip -d disk.flag.img.gz 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls 
disk.flag.img
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ mmls disk.flag.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ fls disk.flag.img -o 411648               
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ fls disk.flag.img -o 411648 -r | grep flag                                         
+ r/r * 1876(realloc):  flag.txt
+ r/r 1782:     flag.txt.enc
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ fls disk.flag.img -o 411648 -r > files    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ vi files
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ icat disk.flag.img -o 411648 1875
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ openssl aes256 -salt -out flag.txt -in flag.txt.enc -k unbreakablepassword1234567 -d
Can't open "flag.txt.enc" for reading, No such file or directory
40474533657F0000:error:80000002:system library:BIO_new_file:No such file or directory:../crypto/bio/bss_file.c:67:calling fopen(flag.txt.enc, rb)
40474533657F0000:error:10000080:BIO routines:BIO_new_file:no such file:../crypto/bio/bss_file.c:75:
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls
disk.flag.img  files
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ icat disk.flag.img -o 411648 1782 > flag.txt.enc
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ openssl aes256 -salt -out flag.txt -in flag.txt.enc -k unbreakablepassword1234567 -d
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40B7DFC65D7F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls
disk.flag.img  files  flag.txt  flag.txt.enc
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ cat flag.txt
picoCTF{h4un71ng_p457_5113beab} 
```