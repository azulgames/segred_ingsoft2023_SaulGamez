## titulo
### Objetivos 
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/217/pico.flag.png)

### Pistas
1. We know the end sequence of the message will be `$t3g0`.

### Solución 

- Descargamos la imagen y la analizamos con zsteg

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ zsteg -a pico.flag.png
b1,r,lsb,xy         .. text: "~__B>VG?G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"

```


picoCTF{7h3r3_15_n0_5p00n_a9a181eb}

### Notas adicionales:

### Referencias:
