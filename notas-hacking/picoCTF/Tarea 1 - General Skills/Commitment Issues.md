# Commitment Issues
I accidentally wrote the flag down. Good thing I deleted it! You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/137/challenge.zip)
Version control can help you recover files if you change or lose them!
Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
You can 'checkout' commits to see the files inside them

## Solución
Con la terminal de kali linux
```
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la 
total 28
drwxrwxr-x 2 kali kali  4096 Feb 20 17:33 .
drwxrwxr-x 6 kali kali  4096 Feb 20 17:33 ..
-rw-rw-r-- 1 kali kali 19197 Feb 20 17:32 challenge.zip
                                                                                                                                                                       
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
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/fc/
 extracting: drop-in/.git/objects/fc/a28bbf8dde2f49246166ae6512a1046fc4cbc3  
   creating: drop-in/.git/objects/61/
 extracting: drop-in/.git/objects/61/db7d05a8b7657aedc1e13320ca53623a364fe7  
   creating: drop-in/.git/objects/ea/
 extracting: drop-in/.git/objects/ea/859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/ef/
 extracting: drop-in/.git/objects/ef/0b7cc6b98367fa168573c931e0f7098ef59182  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la
total 32
drwxrwxr-x 3 kali kali  4096 Feb 20 17:33 .
drwxrwxr-x 6 kali kali  4096 Feb 20 17:33 ..
-rw-rw-r-- 1 kali kali 19197 Feb 20 17:32 challenge.zip
drwxr-xr-x 3 kali kali  4096 Mar 11  2024 drop-in
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ cd drop-in 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Mar 11  2024 .
drwxrwxr-x 3 kali kali 4096 Feb 20 17:33 ..
drwxr-xr-x 8 kali kali 4096 Mar 11  2024 .git
-rw-r--r-- 1 kali kali   11 Mar 11  2024 message.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ cat message.txt  
TOP SECRET
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git log 
commit ef0b7cc6b98367fa168573c931e0f7098ef59182 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    remove sensitive info

commit ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:06:20 2024 +0000

    create flag
    
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git checkout ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0
Note: switching to 'ea859bf3b5d94ee74ce5ee1afa3edd7d4d6b35f0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at ea859bf create flag
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Feb 20 17:36 .
drwxrwxr-x 3 kali kali 4096 Feb 20 17:33 ..
drwxr-xr-x 8 kali kali 4096 Feb 20 17:36 .git
-rw-rw-r-- 1 kali kali   27 Feb 20 17:36 message.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ cat message.txt 
picoCTF{s@n1t1z3_cf09a485}

```