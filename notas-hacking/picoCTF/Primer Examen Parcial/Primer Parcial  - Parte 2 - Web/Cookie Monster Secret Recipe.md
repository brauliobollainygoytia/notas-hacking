# Cookie Monster Secret Recipe
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe? You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:56241/) and good luck
Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?
Cookies aren't just for eating - they're also used in web technologies!
Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.

## Solucion
1. Entrar al sitio 
2. Loggearse
3. inspeccionar el sitio para encontrar las cookies 
4. Copiar la cookie
5. Decodificar la cookie en la terminal de kali linux, esa es la bandera
```
┌──(kali㉿kali)-[~]
└─$ echo -n "cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzZDMkZCN0YzfQ==" | base64 -d
picoCTF{c00k1e_m0nster_l0ves_c00kies_6C2FB7F3}  
```