# c0rrupt
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
Try fixing the file header

## Solución
Con la terminal de Kali Linux, hexeditor y pngcheck, cambiando valores hexadecimales a los correctos
```
──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery'
--2025-04-07 13:10:24--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’

mystery              100%[===================>] 198.18K   878KB/s    in 0.2s    

2025-04-07 13:10:25 (878 KB/s) - ‘mystery’ saved [202940/202940]

                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ file mystery                                
mystery: data
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ xxd mystery | head
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ hexeditor mystery   
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ file mystery      
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ open mystery 
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ sudo apt install pngcheck           
[sudo] password for kali: 
Sorry, try again.
[sudo] password for kali: 
The following packages were automatically installed and are no longer required:
  libbfio1                     libgtksourceviewmm-3.0-0v5
  libc++1-19                   libhdf5-hl-100t64
  libc++abi1-19                libjxl0.9
  libcapstone4                 libmbedcrypto7t64
  libconfig++9v5               libpaper1
  libconfig9                   libsuperlu6
  libdirectfb-1.7-7t64         libtag1v5
  libegl-dev                   libtag1v5-vanilla
  libfmt9                      libtagc0
  libgl1-mesa-dev              libunwind-19
  libgles-dev                  libwebrtc-audio-processing1
  libgles1                     libx265-209
  libglvnd-core-dev            openjdk-23-jre
  libglvnd-dev                 openjdk-23-jre-headless
  libgtksourceview-3.0-1       python3-appdirs
  libgtksourceview-3.0-common
Use 'sudo apt autoremove' to remove them.

Installing:
  pngcheck
                                                                                 
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 120
  Download size: 68.6 kB
  Space needed: 208 kB / 58.4 GB available

Get:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3 [68.6 kB]
Fetched 68.6 kB in 1s (63.4 kB/s)
Selecting previously unselected package pngcheck.
(Reading database ... 419644 files and directories currently installed.)
Preparing to unpack .../pngcheck_3.0.3-3_amd64.deb ...
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ hexeditor mystery  
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ hexeditor mystery  
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ open mystery 

picoCTF{c0rrupt10n_1847995}
```