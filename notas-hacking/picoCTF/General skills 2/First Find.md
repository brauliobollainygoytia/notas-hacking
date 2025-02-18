# First Find
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/501/files.zip)

## Solucion
Con la terminal de kali linux
```──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ ls -la
total 3912
drwxrwxr-x 2 kali kali    4096 Feb 18 16:51 .
drwxrwxr-x 5 kali kali    4096 Feb 17 11:05 ..
-rw-rw-r-- 1 kali kali 3995553 Feb 18 16:51 files.zip
-rw-rw-r-- 1 kali kali       0 Feb 18 12:30 .ltdis.x86_64.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ unzip files.zip           
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: files/satisfactory_books/23765.txt.utf-8  
  inflating: files/satisfactory_books/16021.txt.utf-8  
  inflating: files/13771.txt.utf-8   
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
  inflating: files/adequate_books/more_books/1023.txt.utf-8  
  inflating: files/adequate_books/46804-0.txt  
  inflating: files/adequate_books/44578.txt.utf-8  
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8  
  inflating: files/acceptable_books/17880.txt.utf-8  
  inflating: files/acceptable_books/17879.txt.utf-8  
  inflating: files/14789.txt.utf-8
  ┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills2]
└─$ cd files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/               
                                                                                                                                                                      
┌──(kali㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ ls -la
total 12
drwxrwxr-x 2 kali kali 4096 May 13  2022 .
drwxrwxr-x 3 kali kali 4096 May 13  2022 ..
-rw-rw-r-- 1 kali kali   31 May 13  2022 uber-secret.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/…/more_books/.secret/deeper_secrets/deepest_secrets]
└─$ cat uber-secret.txt                                                                 
picoCTF{f1nd_15_f457_ab443fd1}

```
