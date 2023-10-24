## WebNet1
### Objetivos 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

### Pistas
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

### Solución 
- descargamos el paquete y la llave
- analizamos el paquete con wireshark y vemos que la informacion que viaja por el paquete está encriptada.
- vamos a introducir la llave llendo a Edit > Preferences > Protocols > TLS > agregamos la llave.
- notamos que el paquete 47 contiene una imagen y la exportamos 
- la aplicamos un Strings a la imagen y obtenemos la bandera.

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ strings vulture.jpg | grep pico
picoCTF{honey.roasted.peanuts}

```

### Solucion por consola
``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_

```
picoCTF{honey.roasted.peanuts}
### Notas adicionales:

### Referencias:
TLS: https://es.wikipedia.org/wiki/Seguridad_de_la_capa_de_transporte