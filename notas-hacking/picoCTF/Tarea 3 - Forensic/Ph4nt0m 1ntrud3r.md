# Ph4nt0m 1ntrud3r
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/960abba2fdbc9be5013ef87f1df67213e9b63d4561d7a8c8c1ce7a4ce40a547e/myNetworkTraffic.pcap) and try to get the flag.
Filter your packets to narrow down your search.
Attacks were done in timely manner.
Time is essential

## Solución
Con la terminal de Kali Linux y tshark
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/960abba2fdbc9be5013ef87f1df67213e9b63d4561d7a8c8c1ce7a4ce40a547e/myNetworkTraffic.pcap
--2025-05-11 13:26:33--  https://challenge-files.picoctf.net/c_verbal_sleep/960abba2fdbc9be5013ef87f1df67213e9b63d4561d7a8c8c1ce7a4ce40a547e/myNetworkTraffic.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 65.9.149.24, 65.9.149.95, 65.9.149.85, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|65.9.149.24|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1452 (1.4K) [application/octet-stream]
Saving to: ‘myNetworkTraffic.pcap’

myNetworkTraffic.pcap                     100%[===================================================================================>]   1.42K  --.-KB/s    in 0s      

2025-05-11 13:26:33 (59.6 MB/s) - ‘myNetworkTraffic.pcap’ saved [1452/1452]

┌──(root㉿kali)-[/home/kali/Documents/srss/forensic]
└─# tshark -r myNetworkTraffic.pcap -Y 'tcp.len==12 || tcp.len==4' -T fields -e frame.time
Running as user "root" and group "root". This could be dangerous.
Mar  5, 2025 21:31:49.254895000 CST
Mar  5, 2025 21:31:49.254664000 CST
Mar  5, 2025 21:31:49.255446000 CST
Mar  5, 2025 21:31:49.256121000 CST
Mar  5, 2025 21:31:49.255667000 CST
Mar  5, 2025 21:31:49.255903000 CST
Mar  5, 2025 21:31:49.255124000 CST
                                                                                                                                                                      
┌──(root㉿kali)-[/home/kali/Documents/srss/forensic]
└─# tshark -r myNetworkTraffic.pcap -Y 'tcp.len==12 || tcp.len==4' -T fields -e frame.time -e tcp.segment_data
Running as user "root" and group "root". This could be dangerous.
Mar  5, 2025 21:31:49.254895000 CST     657a46305833633063773d3d
Mar  5, 2025 21:31:49.254664000 CST     63476c6a62304e5552673d3d
Mar  5, 2025 21:31:49.255446000 CST     587a4d3063336c6664413d3d
Mar  5, 2025 21:31:49.256121000 CST     66513d3d
Mar  5, 2025 21:31:49.255667000 CST     596d68664e484a665a513d3d
Mar  5, 2025 21:31:49.255903000 CST     4e575534597a63345a413d3d
Mar  5, 2025 21:31:49.255124000 CST     626e52666447673064413d3d
                                                                                                                                                                      
┌──(root㉿kali)-[/home/kali/Documents/srss/forensic]
└─# tshark -r myNetworkTraffic.pcap -Y 'tcp.len==12 || tcp.len==4' -T fields -e frame.time -e tcp.segment_data | sort -k4
Running as user "root" and group "root". This could be dangerous.
Mar  5, 2025 21:31:49.254664000 CST     63476c6a62304e5552673d3d
Mar  5, 2025 21:31:49.254895000 CST     657a46305833633063773d3d
Mar  5, 2025 21:31:49.255124000 CST     626e52666447673064413d3d
Mar  5, 2025 21:31:49.255446000 CST     587a4d3063336c6664413d3d
Mar  5, 2025 21:31:49.255667000 CST     596d68664e484a665a513d3d
Mar  5, 2025 21:31:49.255903000 CST     4e575534597a63345a413d3d
Mar  5, 2025 21:31:49.256121000 CST     66513d3d
                                                                                                                                                                      
┌──(root㉿kali)-[/home/kali/Documents/srss/forensic]
└─# tshark -r myNetworkTraffic.pcap -Y 'tcp.len==12 || tcp.len==4' -T fields -e frame.time -e tcp.segment_data | sort -k4 | awk '{print $6}'
Running as user "root" and group "root". This could be dangerous.
63476c6a62304e5552673d3d
657a46305833633063773d3d
626e52666447673064413d3d
587a4d3063336c6664413d3d
596d68664e484a665a513d3d
4e575534597a63345a413d3d
66513d3d
                                                                                                                                                                      
┌──(root㉿kali)-[/home/kali/Documents/srss/forensic]
└─# tshark -r myNetworkTraffic.pcap -Y 'tcp.len==12 || tcp.len==4' -T fields -e frame.time -e tcp.segment_data | sort -k4 | awk '{print $6}' | xxd -p -r
Running as user "root" and group "root". This could be dangerous.
cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfZQ==NWU4Yzc4ZA==fQ==                                                                                                                                                                      
┌──(root㉿kali)-[/home/kali/Documents/srss/forensic]
└─# tshark -r myNetworkTraffic.pcap -Y 'tcp.len==12 || tcp.len==4' -T fields -e frame.time -e tcp.segment_data | sort -k4 | awk '{print $6}' | xxd -p -r | base64 -d
Running as user "root" and group "root". This could be dangerous.
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_e5e8c78d}       
```

### Referencias
https://youtu.be/_YKC5Smffeg?si=z3KhCrtaDc5Xgf8d