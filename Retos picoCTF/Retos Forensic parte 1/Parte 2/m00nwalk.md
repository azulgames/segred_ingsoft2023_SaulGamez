## m00nwalk
### Objetivos 
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.

### Pistas
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option
### Solución 

- obtenemos el archivo y nos damos cuenta que es .wav (audio)
- clonamos un repositorio con la herramienta para desencriptar imágenes SSTV
- ejecutamos el comando de sstv para desencriptar message.wav, y automaticamente detecta el método scottie, y nos genera la imagen.

``` bash
2023-10-16 21:07:05 (3.06 MB/s) - ‘message.wav’ saved [11066998/11066998]

┌──(kali㉿kali)-[~/Retos]
└─$  git clone https://github.com/colaclanth/sstv.git 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162
Receiving objects: 100% (221/221), 1.01 MiB | 1.61 MiB/s, done.
Resolving deltas: 100% (139/139), done.
                                                                                                                                                                           
┌──(kali㉿kali)-[~/Retos/sstv]
└─$ sudo python setup.py install
running install
.
.
.

┌──(kali㉿kali)-[~/Retos/sstv]
└─$ sstv -d ../message.wav -o resultado.png

[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
^[2[sstv] Decoding image...                                   [#######.............................................................................................]  [sstv] Decoding image...                                   [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                                                  
┌──(kali㉿kali)-[~/Retos/sstv]
└─$ open resultado.png 

```

- abrimos la imagen y la rotamos para ver la bandera

picoCTF{beep_boop_im_in_space}

### Notas adicionales:

### Referencias:
herramienta sstv: https://github.com/colaclanth/sstv