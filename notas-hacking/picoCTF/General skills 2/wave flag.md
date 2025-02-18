# wave flag
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information...
This program will only work in the webshell or another Linux computer.
To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm`
Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
-h and --help are the most common arguments to give to programs to get more information from them!
Not every program implements help features like -h and --help.

## Solución 
Con la terminal de kali linux

```
──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm              
--2025-02-18 12:24:30--  https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: ‘warm’

warm                                      100%[===================================================================================>]  10.68K  --.-KB/s    in 0s      

2025-02-18 12:24:32 (189 MB/s) - ‘warm’ saved [10936/10936]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ chmod +x warm  
(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ ./warm   
Hello user! Pass me a -h to learn what I can do!
──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ ./warm -h                
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
```