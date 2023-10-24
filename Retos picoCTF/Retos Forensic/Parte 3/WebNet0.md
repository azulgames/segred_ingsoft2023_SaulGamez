## WebNet0
### Objetivos 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

### Pistas
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

### Solución 

- descargamos el paquete y la llave
- analizamos el paquete con wireshark y vemos que la informacion que viaja por el paquete está encriptada.
- vamos a introducir la llave llendo a Edit > Preferences > Protocols > TLS > agregamos la llave.
- hacemos una busqueda de detalle de paquetes. buscamos picoCTF
- La exportamos como texto imprimible.

picoCTF{nongshim.shrimp.crackers}

### Solución por consola

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ sudo apt install ssldump 

┌──(kali㉿kali)-[~/Retos] (no probado)
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2

picoCTF{nongshim.shrimp.crackers}
```

### Notas adicionales:

### Referencias:
TLS: https://es.wikipedia.org/wiki/Seguridad_de_la_capa_de_transporte