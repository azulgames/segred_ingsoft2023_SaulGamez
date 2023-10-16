## So Meta
### Objetivos 
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).
	
### Pistas
3. What does meta mean in the context of files?
2. Ever heard of metadata?

### Solución 


- descargamos la imagen y vemos los metadatos con el comando Strings

``` bash
(kali㉿kali)-[~/Retos/Forensics/so_meta]
└─$ strings pico_img.png | grep pico                    
picoCTF{s0_m3ta_eb36bf44}

```

### Solucion 2

- instalamos la herramienta `imagemagick`
``` bash
┌──(kali㉿kali)-[~/Retos/Forensics/so_meta]
└─$ identify -verbose pico_img.png 

-
-
-
picoCTF{s0_m3ta_eb36bf44}

```
### Notas adicionales:
exiftool: es otra herramienta para ver los metadatos.
### Referencias:
Metadatos: https://www.adslzone.net/reportajes/tecnologia/metadatos-que-son/