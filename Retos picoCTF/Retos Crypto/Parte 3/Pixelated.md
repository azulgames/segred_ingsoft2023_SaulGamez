## Pixelated

### Objetivos 
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)
### Pistas
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images

### Solución 

- descargamos la herramienta para combinar imagenes y la instalamos en /opt
https://github.com/zardus/ctf-tools/blob/master/stegsolve/install
- abrimos la herramienta con java -jar
- en la interfaz grafica seleccionamos una imagen y seleccionamos la opcion Image combiner.
- navegamos en las opciones de sumar imagenes y seleccionamos add para ver la bandera

``` bash
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
[sudo] password for kali:

┌──(kali㉿kali)-[/opt]
└─$ sudo chmod +x stegsolve.jar 

┌──(kali㉿kali)-[~/Retos]
└─$ java -jar stegsolve.jar 
```

picoCTF{d562333d}

### Notas adicionales:

### Referencias:
