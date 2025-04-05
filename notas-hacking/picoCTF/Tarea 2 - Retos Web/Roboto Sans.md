# Roboto Sans
The flag is somewhere on this web application not necessarily on the website. Find it.

## Solución
1. Entrar sitio web
2. Entrar al archivo robots.txt
3. Usando un decodificador de base64, se prueba que hay un archivo en js/myfile.txt
```
┌──(kali㉿kali)-[~]
└─$ echo "anMvbXlmaWxlLnR4dA==" | base64 -d   
js/myfile.txt
```
4. Escribimos esa extención a la dirección y sale la bandera
