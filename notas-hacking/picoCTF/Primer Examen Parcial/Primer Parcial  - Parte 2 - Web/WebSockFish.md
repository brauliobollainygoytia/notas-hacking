# WebSockFish
Can you win in a convincing manner against this chess bot? He won't go easy on you! You can find the challenge [here](http://verbal-sleep.picoctf.net:59467/).
Try understanding the code and how the websocket client is interacting with the server

## Solución
1. Usando el websocket, inspeccionando el sitio, usar la consola y mandar a llamar el método sendMessage para comunicarse con el servidor y que el sitio nos de la bandera, por ejemplo `sendMessage("eval -100000000")`.
2. Al ejecutar en la consola el método, el sitio nos dará la bandera.
