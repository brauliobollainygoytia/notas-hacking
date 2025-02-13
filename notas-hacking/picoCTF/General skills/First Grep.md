Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solucion
Usando la terminal de kali linux
```
┌──(kali㉿kali)-[~/Downloads]
└─$ grep -o 'picoCTF{.*}' file
picoCTF{grep_is_good_to_find_things_5af9d829}

```