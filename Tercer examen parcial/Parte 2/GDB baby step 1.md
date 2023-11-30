### GDB baby step 1

### Objetivos 
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

### Pistas
1. gdb is a very good debugger to use for this problem and many others!
2. `main` is actually a recognized symbol that can be used with gdb commands.

### Solución 

- Le damos permisos de ejecución al programa gdbdebugger_a
- lo ejecutamos con el comando `gdb debugger0_a`,
`(No debugging symbols found in debugger0_a)`
- Utilizaremos el comando `(gdb) layout asm` 
- En en el código vemos la variable `eax` recibiendo el valor hexadecimal 0x86342, que en decimal seria 549698

picoCTF{549698}

### Notas adicionales:

### Referencias:
