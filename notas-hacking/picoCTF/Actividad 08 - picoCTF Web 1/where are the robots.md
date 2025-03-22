# where are the robots
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/56830/` ([link](https://jupiter.challenges.picoctf.org/problem/56830/)) or http://jupiter.challenges.picoctf.org:56830
What part of the website could tell you where the creator doesn't want you to look?

## Solucion
Para este ejercicio lo que tuve que hacer fue entrar a la pagina y despues la grege al link /robots.txt, despues me salio una ventana con información para encontrar la bandera, puse al final del link /1bb4c.html, al completar el link me direcciono a una pagina en donde se encontraba la bandera

```
https://jupiter.challenges.picoctf.org/problem/56830/robots.txt
User-agent: *
Disallow: /1bb4c.html

https://jupiter.challenges.picoctf.org/problem/56830/1bb4c.html
Guess you found the robots  
picoCTF{ca1cu1at1ng_Mach1n3s_1bb4c}

```