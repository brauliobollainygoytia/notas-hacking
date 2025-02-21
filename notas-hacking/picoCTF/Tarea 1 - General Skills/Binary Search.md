# Binary Search
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses. Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools! You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/18/challenge.zip)
Have you ever played hot or cold? Binary search is a bit like that.
You have a very limited number of guesses. Try larger jumps between numbers!
The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?

## Solución
Con la terminal de kali linux
```
┌──(kali㉿kali)-[~]
└─$ ssh -p 59397 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:59397 ([18.217.83.136]:59397)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:17: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:59397' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 200
Higher! Try again.
Enter your guess: 350
Lower! Try again.
Enter your guess: 325
Lower! Try again.
Enter your guess: 315
Higher! Try again.
Enter your guess: 320
Lower! Try again.
Enter your guess: 316
Higher! Try again.
Enter your guess: 319
Lower! Try again.
Enter your guess: 318
Congratulations! You guessed the correct number: 318
Here's your flag: picoCTF{g00d_gu355_2e90d29b}
Connection to atlas.picoctf.net closed.
                                           
```
