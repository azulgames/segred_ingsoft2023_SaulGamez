## Shark on wire 1
### Objetivos 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

### Pistas
1. Try using a tool like Wireshark
2. What are streams?

### Solución 

leemos el archivo con wiresharck 

``` bash
┌──(kali㉿kali)-[~/hacking/pico]
└─$ wireshark capture.pcap
```

seleccionamos el primer paquete UDP, y seguimos el stream de comunicación
saltamos al stream 6 y encontramos la bandera

picoCTF{StaT31355_636f6e6e}

### Notas adicionales:

archivo pcap: captura de paquetes ethernet.
programa wireshark: analiza trafico de red.

### Referencias:
archivo pcap: https://www.reviversoft.com/es/file-extensions/pcap