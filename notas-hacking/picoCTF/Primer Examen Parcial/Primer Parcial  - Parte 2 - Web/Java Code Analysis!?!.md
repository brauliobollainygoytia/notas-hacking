# Java Code Analysis!?!
BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!
Here are the credentials to get you started:
- Username: "user"
- Password: "user"
Source code can be downloaded [here](https://artifacts.picoctf.net/c/483/bookshelf-pico.zip). Website can be accessed [here!](http://saturn.picoctf.net:53573/).
Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
The 'role' and 'userId' fields in the JWT can be of interest to you!
The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.
## Solución
1. Entrar al sitio
2. Loggearse como indica la descripción
3. Seleccionar el libro flag
4. Para acceder como admin debemos de editar las petición
5. Con jwt, editar la petición, cambiando el role, user id, email y la contraseña
6. Una vez editada pegarla en el almacenamiento local y recargar el sitio
7. El sitio mostrara la bandera
Great job! Here’s your flag:picoCTF{w34k_jwt_n0t_g00d_42f5774a}
