# n0s4n1ty 1
A developer has added profile picture upload functionality to a website. However, the implementation is flawed, and it presents an opportunity for you. Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.
File upload was not sanitized
Whenever you get a shell on a remote machine, check `sudo`

## Solución
1. Entrar al sitio
2. Usar y subir un simple-backdoor.php al sitio como si fuera una imagen
3. El sitio nos dará un link para poder acceder al sitio como si fuera una terminal completando la dirección
4. Ejecutar el comando sudo cat /root/flag.txt donde esta la bandera
5. El sitio mostrara la bandera
