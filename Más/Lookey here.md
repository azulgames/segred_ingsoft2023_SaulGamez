## Lookey here

### Objetivos 
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/126/anthem.flag.txt).

### Pistas
1. Download the file and search for the flag based on the known prefix.

### Solución 

``` bash
saulgamez-picoctf@webshell:~$ cat anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}
```

### Notas adicionales:
despues de descargar el archivo solicitado lo leemos con `cat` y lo pasamos por grep para buscar la bandera

### Referencias:
