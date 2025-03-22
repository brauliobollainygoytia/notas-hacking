# Insp3ct0r
Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/44924/` ([link](https://jupiter.challenges.picoctf.org/problem/44924/)) or http://jupiter.challenges.picoctf.org:44924
How do you inspect web code on a browser?
There's 3 parts
## Solución
Entrar a la pagina y inspeccionar la misma viendo el código fuente, la bandera estaba en un comentario en HTML, la segunda parte de la bandera se encontraba en un comentario de un archivo CSS, y la tercer a parte de la bandera estaba en un comentario de un archivo javascript.
```
<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->

/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */

/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?f10be399} */
```


