# findme
Help us test the form by submiting the username as `test` and password as `test!`
any redirections?

## Solución
1. Entrar al sitio desde el navegador de burpsuite
2. Loggearse con el username test y password test!
3. Darle forward al sitio, nos da un link que esta codificado en base 64
4. Decodificar el código
```┌──(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ echo -n "cGljb0NURntwcm94aWVzX2Fs" | base64 -d                                        
picoCTF{proxies_al
```
5. Seguir dándole forward al sitio, nos dará otro link con la otra parte de la bandera, igual esta codificado en base 64
6. Decodificar el código
```┌──(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ echo -n "bF90aGVfd2F5X2JlNzE2ZDhlfQ==" | base64 -d
l_the_way_be716d8e} 
```
7. Unir las dos partes de la bandera