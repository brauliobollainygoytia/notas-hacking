# MatchTheRegex
How about trying to match a regular expression The website is running [here](http://saturn.picoctf.net:60780/).
Access the webpage and try to match the regular expression associated with the text field

## Solución
1. Entrar al sitio
2. Ver el código fuente
3. En un comentario esta la exprecion regular que se sube en el sitio y que muestra la flag, sera un texto que empiece con p tenga algo después y que termine con F
4. Ingresar el texto y subir al sitio para copiar la bandera
```
3.
// ^p.....F!?
4.
picoCTF{succ3ssfully_matchtheregex_2375af79}
```
