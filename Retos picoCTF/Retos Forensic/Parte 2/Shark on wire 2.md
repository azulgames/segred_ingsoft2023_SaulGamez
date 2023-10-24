## Shark on wire 2
### Objetivos 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

### Pistas
none

### Solución 

- descargamos el archivo pcap
- lo abrimos en wireshark y rastreamos un paquete UDP.
- Navegando en los paquetes encontramos una marca de start y de end en el puerto destino 22.
- filtramos los paquetes con destino en el puerto 22 con: 
	udp.dstport == 2
- si decodificamos cada puerto destino restando 5000, encontramos la bandera codificada.

la forma de automatizar esto con python:

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ nano exp.py
                  
┌──(kali㉿kali)-[~/Retos]
└─$ python3 exp.py  

picoCTF{p1LLf3r3d_data_v1a_st3g0}
```

script exp.py:
``` python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag += chr(p[UDP].sport - 5000)

print(flag)
```

picoCTF{p1LLf3r3d_data_v1a_st3g0}
### Notas adicionales:

### Referencias: