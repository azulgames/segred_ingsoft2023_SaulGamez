## What Lies Within
### Objetivos 
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

### Pistas
1. There is data encoded somewhere... there might be an online decoder.

### Solución 

abrimos una pagina que nos ayude a decodificar la imagen
https://stylesuxx.github.io/steganography/
y obtenemos la bandera
picoCTF{h1d1ng_1n_th3_b1t5}


también podemos utilizar una herramienta de linux en rubi, para decodificar la bandera
``` bash
zsteg -a buildings.png
```

### Notas adicionales:



### Referencias:
decodificador de stegonografia online: https://stylesuxx.github.io/steganography/