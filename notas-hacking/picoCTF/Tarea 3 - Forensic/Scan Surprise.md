# Scan Surprise
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/16/challenge.zip)
Additional details will be available after launching your challenge instance.
QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
If you don't have access to a phone, you can also use zbar-tools to convert an image to text
## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~/…/srss/forensic/_flag.png.extracted/secret]
└─$ ssh -p 63104 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:63104 ([18.217.83.136]:63104)' can't be established.
ED25519 key fingerprint is SHA256:hVmbk/OaNT4902bBr7h26wfhmBuJWi4tub8AJqoAJCM.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[atlas.picoctf.net]:63104' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
                                                                  
ctf-player@challenge:~/drop-in$ ls
flag.png
ctf-player@challenge:~/drop-in$ zbarimg flag.png 
Connection Error (Failed to connect to socket /var/run/dbus/system_bus_socket: No such file or directory)
Connection Null
QR-Code:picoCTF{p33k_@_b00_7843f77c}
scanned 1 barcode symbols from 1 images in 0 seconds

ctf-player@challenge:~/drop-in$ Connection to atlas.picoctf.net closed by remote host.
Connection to atlas.picoctf.net closed.

```