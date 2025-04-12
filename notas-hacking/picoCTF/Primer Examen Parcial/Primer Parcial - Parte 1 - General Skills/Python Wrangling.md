# Python Wrangling
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py) using [this password](https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt) to get [the flag](https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en)?
Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py`
`$ man python`

## Solución
Con la terminal de Kali linux y python
```
┌──(kali㉿kali)-[~/Documents/srss]
└─$ cd GeneralSkills 
                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ wget 'https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py'
--2025-04-08 15:32:30--  https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/ende.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: ‘ende.py’

ende.py              100%[===================>]   1.30K  --.-KB/s    in 0s      

2025-04-08 15:32:30 (21.9 MB/s) - ‘ende.py’ saved [1328/1328]

                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ wget 'https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt'
--2025-04-08 15:32:52--  https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/pw.txt
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: ‘pw.txt’

pw.txt               100%[===================>]      33  --.-KB/s    in 0s      

2025-04-08 15:32:53 (24.6 MB/s) - ‘pw.txt’ saved [33/33]

                                                                                 
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ wget 'https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en'
--2025-04-08 15:33:28--  https://mercury.picoctf.net/static/b351a89e0bc6745b00716849105f87c6/flag.txt.en
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: ‘flag.txt.en’

flag.txt.en          100%[===================>]     140  --.-KB/s    in 0s      

2025-04-08 15:33:29 (132 MB/s) - ‘flag.txt.en’ saved [140/140]

──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ python ende.py -d flag.txt.en 
Please enter the password:67c6cc9667c6cc9667c6cc9667c6cc96
picoCTF{4p0110_1n_7h3_h0us3_67c6cc96}

──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ cat pw.txt 
67c6cc9667c6cc9667c6cc9667c6cc96
```