What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solucion
Con python
```
python
Python 3.12.8 (main, Feb  1 2025, 21:32:22) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
>>> import base64
>>> print(base64.b64decode("bDNhcm5fdGgzX3IwcDM1").decode("utf-8"))
l3arn_th3_r0p35

picoCTF{l3arn_th3_r0p35}
```