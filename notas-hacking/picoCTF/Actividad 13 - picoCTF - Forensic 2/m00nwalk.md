# m00nwalk
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.
How did pictures from the moon landing get sent back to Earth?
What is the CMU mascot?, that might help select a RX option

## Solución
Con kali linux y un decodificador sstv
```
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav'  
--2025-04-06 14:32:47--  https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav                               100%[==================================================================================>]  10.55M  3.18MB/s    in 3.5s    

2025-04-06 14:32:51 (3.04 MB/s) - ‘message.wav’ saved [11066998/11066998]

                                                                                                                                                                     
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ sstv -d message.wav -o result.png        
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                  [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                                                     
┌──(kali㉿kali)-[~/Documents/srss/forensic]
└─$ open result.png 
picoCTF{beep_boop_im_in_space}
```
