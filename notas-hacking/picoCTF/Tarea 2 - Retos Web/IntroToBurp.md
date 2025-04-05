# IntroToBurp
Try [here](http://titan.picoctf.net:59958/) to find the flag
Try using burpsuite to intercept request to capture the flag.
Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

## Solucion
1. Abrir burp, dirigirse a proxy, abrir el navegador, activar la intercepción, entrar al sitio desde el navegador de burp
2. El sitio dará un formulario para registrar datos, registrarlos
3. Dar forward hasta que el sitio muestre un formulario para guardar una otp
4. Dar forward hasta que diga error
5. Borrar la parte del código donde se guardo el otp
6. Dar forward, el sitio mostrara la bandera