# JaWT Scratchpad
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864
What is that cookie?
Have you heard of JWT?

## Solución
1. Entrar al sitio y logearse
2. Usando Cookie editor copiar el jwt que genera
3. Guardar el jwt en un archivo llamando hash
4. Usando el programa john, descubrir el contraseña del admin con combinaciones que están guardadas en un archivo llamado rockyou.txt que se encuentra en la carpeta /usr/share/wordlists
5. Cambiar de usuario a admin y poner la contraseña de admin
6. Guardar el nuevo jwt en la cookie y recargar el sitio, aparecerá la bandera
```
 3.
 nano hash
 ┌──(kali㉿kali)-[~]
└─$ cat hash        
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYnJhdWxpbyJ9.81jdRg6nNZiSKK9FWTDOZVBLkUMqlgJ23du3N2OxQAk

4.
la contrasena es ilovepico
5.
{
  "user": "admin"
}
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  
) secret base64 encoded

6.
picoCTF{jawt_was_just_what_you_thought_1ca14548}
```