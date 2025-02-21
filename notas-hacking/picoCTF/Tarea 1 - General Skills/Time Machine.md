# Time Machine
What was I last working on? I remember writing a note to help me remember... You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/162/challenge.zip)
The `cat` command will let you read a file, but that won't help you here!
Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
When committing a file with git, a message can (and should) be included.

## Solución
Con la terminal de kali linux
```
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la
total 8
drwxrwxr-x 2 kali kali 4096 Feb 20 17:44 .
drwxrwxr-x 6 kali kali 4096 Feb 20 17:33 ..
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la
total 28
drwxrwxr-x 2 kali kali  4096 Feb 20 17:45 .
drwxrwxr-x 6 kali kali  4096 Feb 20 17:45 ..
-rw-rw-r-- 1 kali kali 17739 Feb 20 17:45 challenge.zip
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
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
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/71/
 extracting: drop-in/.git/objects/71/2314f105348e295f8cadd7d7dc4e9fa871e9a2  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ ls -la
total 32
drwxrwxr-x 3 kali kali  4096 Feb 20 17:45 .
drwxrwxr-x 6 kali kali  4096 Feb 20 17:45 ..
-rw-rw-r-- 1 kali kali 17739 Feb 20 17:45 challenge.zip
drwxr-xr-x 3 kali kali  4096 Mar 11  2024 drop-in
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General]
└─$ cd drop-in 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Mar 11  2024 .
drwxrwxr-x 3 kali kali 4096 Feb 20 17:45 ..
drwxr-xr-x 8 kali kali 4096 Mar 11  2024 .git
-rw-r--r-- 1 kali kali   87 Mar 11  2024 message.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/General/drop-in]
└─$ git show                                             
commit 712314f105348e295f8cadd7d7dc4e9fa871e9a2 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:26 2024 +0000

    picoCTF{t1m3m@ch1n3_e8c98b3a}

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..4324621
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+This is what I was working on, but I'd need to look at my commit history to know why...
\ No newline at end of file

```
