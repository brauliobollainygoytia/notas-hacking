# Super SSH
Using a Secure Shell (SSH) is going to be pretty important.
Additional details will be available after launching your challenge instance.
[https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)
You can try logging in 'as' someone with `<user>`@titan.picoctf.net
How could you specify the port?
Remember, passwords are hidden when typed into the shell

## Solucion
Con la terminal de kali linux
```
┌──(kali㉿kali)-[~/Documents/srss]
└─$ ssh ctf-player@titan.picoctf.net -p 64507
The authenticity of host '[titan.picoctf.net]:64507 ([3.139.174.234]:64507)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:64507' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_8969f7d3}
Connection to titan.picoctf.net closed.

```