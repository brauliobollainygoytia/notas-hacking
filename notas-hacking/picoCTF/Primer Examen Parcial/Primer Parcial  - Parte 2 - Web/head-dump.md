# head-dump
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag. The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.
Explore backend development with us
The head was dumped.

## Solución
1. Entrar al sitio.
2. En un hashtag viene un link para ver la documentación, entrar al link
3. En la api del sitio dirigirse a la parte de diagnosing, tratar de ejcutar el codigo del sitio
4. Al tratar de ejecutar el codigo, el sitio proporcionara un archivo que hay que descargar
5. Descargar el archivo
6. En la terminal de kali linux hacerle un cat a ese archivo y filtrarlo para encontrar la bandera
```
┌──(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ cat heapdump-1744398778178.heapsnapshot | grep picoCTF{
picoCTF{Pat!3nt_15_Th3_K3y_388d10f7}

```
