## Extensions
### Objetivos 
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

### Pistas
1. How do operating systems know what kind of file it is? (It's not just the ending!

### Solución 

hacemos un cat para ver el contenido del archivo

``` bash
┌──(kali㉿kali)-[~/hacking/pico]
└─$ cat flag.txt 
�PNG
.
.
.
```

 parece que es un archivo PNG entonces le cambiamos la extensión
``` bash
┌──(kali㉿kali)-[~/hacking/pico]
└─$ mv flag.txt flag.PNG
```

abrimos la imagen y vemos la bandera:
picoCTF{now_you_know_about_extensions}


también podemos ver los magic bits con xxd:
```
┌──(kali㉿kali)-[~/hacking/pico]
└─$ xxd flag.PNG 
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
```

### Notas adicionales:

mediante los magic bites podemos saber que tipo de archivo es

### Referencias:
