## tunn3l v1s10n
### Objetivos 
We found this [file](https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n). Recover the flag.
### Pistas
1. Weird that it won't display right...

### Solución 

- descargamos el archivo y vemos que tipo de datos contiene.
- el encavezado nos sugiere que es un archivo BMP

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ file tunn3l_v1s10n      
tunn3l_v1s10n: data
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Retos]
└─$ xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.

```

- vemos que tenemos un bmp de windows.
- editamos con el editor exadecimal el tamaño del encabezado (40 bytes)

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ hexeditor tunn3l_v1s10n 
                                                                 
┌──(kali㉿kali)-[~/Retos]
└─$ xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 2800 0000 2800  BM.&,.....(...(.
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.
                                                                  
┌──(kali㉿kali)-[~/Retos]
└─$ open tunn3l_v1s10n
```
- vemos que la imagen ya ha sido reparada y la podemos abrir, pero no econtramos la bandera.

- vemos sus metadatos y nos percatamos de que el tamaño es poco alto y no coincide con las dimensiones especificadas, entonces lo corregimos.
``` bash

┌──(kali㉿kali)-[~/Retos]
└─$ exiftool tunn3l_v1s10n                                                                                                                                          
ExifTool Version Number         : 12.65
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2023:10:23 23:19:22-04:00
File Access Date/Time           : 2023:10:23 23:19:27-04:00
File Inode Change Date/Time     : 2023:10:23 23:19:22-04:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x306
Megapixels                      : 0.347

┌──(kali㉿kali)-[~/Retos]
└─$ hexeditor tunn3l_v1s10n
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Retos]
└─$ xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 2800 0000 2800  BM.&,.....(...(.
00000010: 0000 6e04 0000 4004 0000 0100 1800 0000  ..n...@.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Retos]
└─$ open tunn3l_v1s10n 

```
- encontramos la bandera en la parte que no se mostraba de la imagen

picoCTF{qu1t3_a_v13w_2020}

### Notas adicionales:

### Referencias:
BMP: https://es.wikipedia.org/wiki/Windows_bitmap