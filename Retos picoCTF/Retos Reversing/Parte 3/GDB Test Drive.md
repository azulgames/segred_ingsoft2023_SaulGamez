### GDB Test Drive

### Objetivos 
Can you get the flag?

Download this [binary](https://artifacts.picoctf.net/c/85/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
### Pistas
none

### Solución 

- descargamos el programa y seguimos las instrucciones.

modificamos los permisos del programa, establecemos un punto de detención, corremos el programa y saltamos al la línea de código que nos muestra la bandera.
``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ chmod -R 777 gdbme         

                                                                                 
┌──(kali㉿kali)-[~/Retos]
└─$  gdb gdbme
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)

(gdb) break *(main+99)
Breakpoint 1 at 0x132a

(gdb) break *(main+99)
Note: breakpoint 1 also set at pc 0x132a.
Breakpoint 2 at 0x132a

(gdb) run
Starting program: /home/kali/Retos/gdbme 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000055555555532a in main ()

(gdb) jump *(main+104)
Continuing at 0x55555555532f.
picoCTF{d3bugg3r_dr1v3_197c378a}
[Inferior 1 (process 32799) exited normally]
(gdb) 

```

picoCTF{d3bugg3r_dr1v3_197c378a}

### Notas adicionales:

### Referencias:
