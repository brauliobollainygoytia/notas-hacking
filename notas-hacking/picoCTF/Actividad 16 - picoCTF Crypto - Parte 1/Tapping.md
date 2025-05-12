# Tapping
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 48247`.
What kind of encoding uses dashes and dots?
The flag is in the format PICOCTF{}

## Solución
Con la terminal de kali linux y CyberChef
```
┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ nc jupiter.challenges.picoctf.org 48247
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .---- ..--- -.... .---- ....- ...-- ---.. .---- ---.. .---- } 

┌──(kali㉿kali)-[~/Documents/srss/crypto]
└─$ nc jupiter.challenges.picoctf.org 48247 | xclip -selection c

PICOCTFM0RS3C0D31SFUN1261438181 
picoCTF{M0RS3C0D31SFUN1261438181}
```

### Referencias
https://youtu.be/g1bGxseNsxA?si=TWC0gugkSUTiOc-8