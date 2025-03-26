# Scavenger Hunt
There is some interesting information hidden around this site [http://mercury.picoctf.net:39698/](http://mercury.picoctf.net:39698/). Can you find it?
You should have enough hints to find the files, don't run a brute forcer.

## Solución
1. Inspeccionando el código fuente.
2. Entrando al código CSS.
3. Entrando al archivo javascript y accediendo al archivo robots.txt del sitio
4. Accediendo al archivo .htaccess del sitio
5.  Accediendo al archivo .DS_Store
```
1.
<!-- Here's the first part of the flag: picoCTF{t -->
2.
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
3.
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
4.
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
5.
Congrats! You completed the scavenger hunt. Part 5: _fa04427c}
```