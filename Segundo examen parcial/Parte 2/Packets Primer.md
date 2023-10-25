### Packets Primer
### Objetivos 
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/196/network-dump.flag.pcap)
### Pistas
1. Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

### Solución 

- abrimos la captura de paquetes con Wireshark y hacemos un follow stream a el primer paquete TCP y obtenemos la bandera
	p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }

picoCTF{p4ck37_5h4rk_01b0a0d6}

### Notas adicionales:

### Referencias:
