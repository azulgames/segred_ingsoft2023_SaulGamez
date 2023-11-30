### Bit-O-Asm-4

### Objetivos 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

### Pistas
1. Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.
2. Of course, if you're really good, you'll only need one attempt to solve this problem.

### Solución 

- Se compara si 0x9fe1a es menor igual a 0x2710, lo que es falso, por lo que no se cumple la condición.
- Le restamos 0x65 a 0x9fe1a
- se saltara a <main+41>, donde se asigna el resultado a la variable `eax` que es 0x9fdb5, en decimal seria: 654773


picoCTF{654773}

### Notas adicionales:

### Referencias:
