# Based
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.
I hear python can convert things.
It might help to have multiple windows open.

## Solución 
Con la terminal de kali y python
```
nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
lamp
Please give the 01101100 01100001 01101101 01110000 as a word.
...
you have 45 seconds.....

Input:
lamp
Please give me the  141 156 151 155 141 164 151 157 156 as a word.
Input:
animation
Please give me the 636f6d7075746572 as a word.
Input:
computer
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}

binario = "01101100 01100001 01101101 01110000".split(" ")

for i in binario:
    print(chr(int(i,2)), end="")
print()

octal = "141 156 151 155 141 164 151 157 156".split(" ")

for i in octal:
    print(chr(int(i, 8)), end="")

# hexadecimal
print(bytes.fromhex("636f6d7075746572").decode("utf-8"))

```