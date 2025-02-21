# Collaborative Development
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)
`git branch -a` will let you see available branches
How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

## Solucion
Con la terminal de kali linux 
```
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ wget https://artifacts.picoctf.net/c_titan/176/challenge.zip
--2025-02-20 18:23:01--  https://artifacts.picoctf.net/c_titan/176/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 2600:9000:25ed:a200:16:5ec5:2840:93a1, 2600:9000:25ed:2200:16:5ec5:2840:93a1, 2600:9000:25ed:cc00:16:5ec5:2840:93a1, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|2600:9000:25ed:a200:16:5ec5:2840:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24474 (24K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                             100%[===================================================================================>]  23.90K  --.-KB/s    in 0.001s  

2025-02-20 18:23:02 (31.7 MB/s) - ‘challenge.zip’ saved [24474/24474]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
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
...

┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la
total 36
drwxrwxr-x 3 kali kali  4096 Feb 20 18:26 .
drwxrwxr-x 6 kali kali  4096 Feb 20 18:03 ..
-rw-rw-r-- 1 kali kali 24474 Mar 11  2024 challenge.zip
drwxr-xr-x 3 kali kali  4096 Mar 11  2024 drop-in
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ cd drop-in 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Mar 11  2024 .
drwxrwxr-x 3 kali kali 4096 Feb 20 18:26 ..
-rw-r--r-- 1 kali kali   30 Mar 11  2024 flag.py
drwxr-xr-x 8 kali kali 4096 Mar 11  2024 .git
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ cat flag.py   
print("Printing the flag...")
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git branch        
  feature/part-1
  feature/part-2
  feature/part-3
* main

┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git checkout feature/part-1
Switched to branch 'feature/part-1'
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Feb 20 18:29 .
drwxrwxr-x 3 kali kali 4096 Feb 20 18:26 ..
-rw-rw-r-- 1 kali kali   64 Feb 20 18:29 flag.py
drwxr-xr-x 8 kali kali 4096 Feb 20 18:29 .git
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ python flag.py      
Printing the flag...
picoCTF{t3@mw0rk_                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git checkout feature/part-2
Switched to branch 'feature/part-2'
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ python flag.py             
Printing the flag...
m@k3s_th3_dr3@m_                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git checkout feature/part-3
Switched to branch 'feature/part-3'
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ python flag.py             
Printing the flag...
w0rk_2c91ca76}

```
