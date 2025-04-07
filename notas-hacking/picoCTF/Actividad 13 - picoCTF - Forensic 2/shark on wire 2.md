# shark on wire 2
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución
Con la terminal de Kali linux, python, scapy y wireshark
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap'
--2025-04-07 14:06:45--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[===================================================================================>] 109.69K   576KB/s    in 0.2s    

2025-04-07 14:06:45 (576 KB/s) - ‘capture.pcap’ saved [112318/112318]

#codigo de python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport==22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport-5000)
print(flag)

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ python exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```
