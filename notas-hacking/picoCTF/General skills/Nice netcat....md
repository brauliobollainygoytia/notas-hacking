# Nice netcat...
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...
You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solucion
Con la terminal de kali linux y python
```
┌──(kali㉿kali)-[~]
└─$ nc mercury.picoctf.net 49039
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
51 
100 
56 
52 
101 
100 
99 
56 
125 
10 
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ python
Python 3.12.8 (main, Feb  1 2025, 21:32:22) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> valores = [112, 105, 99, 111, 67, 84, 70, 123, 103, 48, 48, 100, 95, 107, 49, 116, 116, 121, 33, 95, 110, 49, 99, 51, 95, 107, 49, 116, 116, 121, 33, 95, 51, 100, 56, 52, 101, 100, 99, 56, 125]
>>> 
>>> flag = ''.join(chr(num) for num in valores)
>>> print(flag)
picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}

```
