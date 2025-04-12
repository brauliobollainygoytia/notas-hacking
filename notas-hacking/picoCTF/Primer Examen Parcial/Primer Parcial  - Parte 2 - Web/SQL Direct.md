# SQL Direct
Connect to this PostgreSQL server and find the flag!
What does a SQL database contain?
## Solución
Con la terminal de kali linux
```
┌──(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ psql -h saturn.picoctf.net -p 61686 -U postgres pico
Password for user postgres: 
psql (17.2 (Debian 17.2-1+b2), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# \d 
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# exit

```
