# Milkslap
[🥛](http://mercury.picoctf.net:29522/)
Look at the problem category

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget http://mercury.picoctf.net:29522/concat_v.png                                                     
--2025-05-09 19:56:11--  http://mercury.picoctf.net:29522/concat_v.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:29522... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png                              100%[===================================================================================>]  17.26M  2.55MB/s    in 8.9s    

2025-05-09 19:56:20 (1.93 MB/s) - ‘concat_v.png’ saved [18095920/18095920]

┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ export RUBY_THREAD_VM_STACK_SIZE=500000000    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ zsteg concat_v.png                        
imagedata           .. text: "\n\n\n\n\n\n\t\t"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. zsh: killed     zsteg concat_v.png


```
