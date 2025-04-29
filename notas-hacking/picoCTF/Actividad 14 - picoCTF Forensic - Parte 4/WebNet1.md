# WebNet1
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
Try using a tool like Wireshark.
How can you decrypt the TLS stream?

## Solución
Usando la terminal de kali linux
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2025-04-28 16:10:31--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[===================================================================================>]  90.36K   442KB/s    in 0.2s    

2025-04-28 16:10:31 (442 KB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2025-04-28 16:10:53--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                              100%[===================================================================================>]   1.66K  --.-KB/s    in 0s      

2025-04-28 16:10:53 (64.0 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wireshark capture.pcap 
```
#### Usando wire shark
Cargar la key a wireshark para desencriptar los steams, seguir los TLS steams hasta encontrar la bandera
picoCTF{honey.roasted.peanuts}

### Referencias
https://youtu.be/Ym3i79nEHjw?si=6j2Zcn9qeANS7K-Y