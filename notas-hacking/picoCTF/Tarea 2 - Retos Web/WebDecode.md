# WebDecode
Do you know how to use the web inspector?
Use the web inspector on other files included by the web page.
The flag may or may not be encoded

## Solución
1. Entrar al sitio
2. Inspeccionar el código fuente
3. En el archivo about.html se encuentra la bandera pero esta codificada en base 64
4. Decodificar la bandera, con la terminal de kali linux
```
──(kali㉿kali)-[~]
└─$ echo -n "cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9" | base64 -d
picoCTF{web_succ3ssfully_d3c0ded_07b91c79}
```
