# Blame Game
Someone's commits seems to be preventing the program from working. Who is it? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/74/challenge.zip)
In collaborative projects, many users can make many changes. How can you see the changes within one file?
Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.

## Solucion
Con la terminal de kali linux y git
```
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ wget https://artifacts.picoctf.net/c_titan/74/challenge.zip
--2025-02-20 18:15:44--  https://artifacts.picoctf.net/c_titan/74/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:5a00:16:5ec5:2840:93a1, 2600:9000:25ed:c800:16:5ec5:2840:93a1, 2600:9000:25ed:3600:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:5a00:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 294122 (287K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                             100%[===================================================================================>] 287.23K  1.25MB/s    in 0.2s    

2025-02-20 18:15:44 (1.25 MB/s) - ‘challenge.zip’ saved [294122/294122]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la
total 296
drwxrwxr-x 2 kali kali   4096 Feb 20 18:15 .
drwxrwxr-x 6 kali kali   4096 Feb 20 18:03 ..
-rw-rw-r-- 1 kali kali 294122 Mar 11  2024 challenge.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
 extracting: drop-in/message.py      
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/7d/
 extracting: drop-in/.git/objects/7d/f869a15e76c28afb609fa4dbc059144ad70161  
 extracting: drop-in/.git/objects/7d/1a38ce37ac1224ccc8c91b969c1e70b46cbdaa  
 extracting: drop-in/.git/objects/7d/902b62f1ea74a5c3e1ee74fbfb5e1ba2b3a33b
 
...

┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ cd drop-in   

──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git log message.py 
commit 0fe87f16cbd8129ed5f7cf2f6a06af6688665728
Author: picoCTF{@sk_th3_1nt3rn_ea346835} <ops@picoctf.com>
Date:   Sat Mar 9 21:09:25 2024 +0000

    optimize file size of prod code

commit 7e8a2415b6cca7d0d0002ff0293dd384b5cc900d
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:25 2024 +0000

    create top secret project

```