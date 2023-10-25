## Wireshark doo dooo do doo
### Objetivos 
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).

### Pistas
(None)

### Solución 

- analizamos el paquete con wireshark
- hacemos un follow stream de los paquetes TCP y en el quinto encontramos este texto:

Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

- nos damos cuenta que está encriptado en rot13 y lo desciframos:

picoCTF{p33kab00_1_s33_u_deadbeef}

### Notas adicionales:

### Referencias:
rot13: https://rot13.com/