# Disk, disk, sleuth!
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz)
Have you ever used `file` to determine what a file was?
Relevant terminal-fu in picoGym: https://play.picoctf.org/practice/challenge/85
Mastering this terminal-fu would enable you to find the flag in a single command: https://play.picoctf.org/practice/challenge/48
Using your own computer, you could use qemu to boot from this disk!

## Solución
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz
--2025-05-09 13:57:04--  https://mercury.picoctf.net/static/a734f18939e0aaea9d27bc7a243a0ed0/dds1-alpine.flag.img.gz
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768910 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.img.gz                   100%[===================================================================================>]  28.39M  7.46MB/s    in 4.2s    

2025-05-09 13:57:08 (6.77 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768910/29768910]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ gzip -d dds*.gz                            
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ file *.img        
dds1-alpine.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0x10,81,1), startsector 2048, 260096 sectors
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ strings *.img | grep pico                       
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_a69a712c}

```