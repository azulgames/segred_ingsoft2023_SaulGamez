## HideToSee

### Objetivos 
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/238/atbash.jpg).

### Pistas
1. Download the image and try to extract it.

### Solución 

- extraemos la imagen con steghide
- vemos el contenido
``` bash

┌──(kali㉿kali)-[~/Retos]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".

┌──(kali㉿kali)-[~/Retos]
└─$ cat encrypted.txt 

krxlXGU{zgyzhs_xizxp_8z0uvwwx}

```

- tenemos la bandera encriptada en atbash, utilizamos ciberchef para desencriptarla https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfOHowdXZ3d3h9

picoCTF{atbash_crack_8a0feddc}

### Notas adicionales:

### Referencias:
