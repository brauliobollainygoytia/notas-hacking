# CanYouSee
How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/129/unknown.zip).
How can you view the information about the picture?
If something isn't in the expected form, maybe it deserves attention?

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://artifacts.picoctf.net/c_titan/129/unknown.zip
--2025-05-10 12:51:02--  https://artifacts.picoctf.net/c_titan/129/unknown.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.85, 18.154.144.103, 18.154.144.104, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2252200 (2.1M) [application/octet-stream]
Saving to: ‘unknown.zip’

unknown.zip                               100%[===================================================================================>]   2.15M  5.00MB/s    in 0.4s    

2025-05-10 12:51:03 (5.00 MB/s) - ‘unknown.zip’ saved [2252200/2252200]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls -la
total 2208
drwxrwxr-x 2 kali kali    4096 May 10 12:51 .
drwxrwxr-x 7 kali kali    4096 May  9 20:36 ..
-rw-rw-r-- 1 kali kali 2252200 Mar 11  2024 unknown.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ gzip -d unknown.zip 
gzip: unknown.zip: unknown suffix -- ignored
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ gzip unknown.zip        
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls    
unknown.zip.gz
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ gzip -d unknown.zip.gz                                                     
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls
unknown.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ unzip unknown.zip            
Archive:  unknown.zip
  inflating: ukn_reality.jpg         
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ ls -la
total 4420
drwxrwxr-x 2 kali kali    4096 May 10 12:56 .
drwxrwxr-x 7 kali kali    4096 May  9 20:36 ..
-rw-r--r-- 1 kali kali 2263721 Mar 11  2024 ukn_reality.jpg
-rw-rw-r-- 1 kali kali 2252200 Mar 11  2024 unknown.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ eog ukn_reality.jpg 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ exiftool ukn_reality.jpg | grep License | sed -e 's/.*: //' | base64 -d
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ exiftool ukn_reality.jpg                                               
ExifTool Version Number         : 13.10
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 18:05:53-06:00
File Access Date/Time           : 2025:05:10 12:57:09-06:00
File Inode Change Date/Time     : 2025:05:10 12:56:22-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fYjMyMDQwYjh9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ exiftool ukn_reality.jpg | grep Attribution URL | sed -e 's/.*: //' | base64 -d
grep: URL: No such file or directory
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ echo cGljb0NURntNRTc0RDQ3QV9ISUREM05fYjMyMDQwYjh9Cg== | base64 -d                                                                    
picoCTF{ME74D47A_HIDD3N_b32040b8}

```