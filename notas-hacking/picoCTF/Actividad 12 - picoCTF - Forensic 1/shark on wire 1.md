# shark on wire 1
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
Try using a tool like Wireshark
What are streams?

## Solución
Con la terminal de Kali Linux y Wireshark.
1. Abrir wireshark
2. Abrir el archivo pcap en wireshar
3. Seguir el stram UPT hasta enontrar la bandera
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap'        
--2025-04-02 18:18:19--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[===================================================================================>] 233.84K   666KB/s    in 0.4s    

2025-04-02 18:18:20 (666 KB/s) - ‘capture.pcap’ saved [239455/239455]

```