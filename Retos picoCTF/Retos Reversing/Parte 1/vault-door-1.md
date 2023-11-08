## vault-door-1

### Objetivos 
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java)

### Pistas
1. Look up the charAt() method online.

### Solución

- Extraemos la parte de la validacion del codigo java que se nos proporciona para pegarlo en un archivo diferente.
- Le agregamos un 0 a los charAt que tengan solo un digito para ordenarlos con facilidad.

```
┌──(kali㉿kali)-[~/Retos]
└─$ touch txt.txt    
                                                                        
┌──(kali㉿kali)-[~/Retos]
└─$ nano txt.txt    
                                                                           
┌──(kali㉿kali)-[~/Retos]
└─$ cat txt.txt | sort 
               password.charAt(00)  == 'd' &&
               password.charAt(01)  == '3' &&
               password.charAt(02)  == '5' &&
               password.charAt(03)  == 'c' &&
               password.charAt(04)  == 'r' &&
               password.charAt(05)  == '4' &&
               password.charAt(06)  == 'm' &&
               password.charAt(07)  == 'b' &&
               password.charAt(08)  == 'l' &&
               password.charAt(09)  == '3' &&
               password.charAt(10) == '_' &&
               password.charAt(11) == 't' &&
               password.charAt(12) == 'H' &&
               password.charAt(13) == '3' &&
               password.charAt(14) == '_' &&
               password.charAt(15) == 'c' &&
               password.charAt(16) == 'H' &&
               password.charAt(17) == '4' &&
               password.charAt(18) == 'r' &&
               password.charAt(19) == '4' &&
               password.charAt(20) == 'c' &&
               password.charAt(21) == 'T' &&
               password.charAt(22) == '3' &&
               password.charAt(23) == 'r' &&
               password.charAt(24) == '5' &&
               password.charAt(25) == '_' &&
               password.charAt(26) == '7' &&
               password.charAt(27) == '5' &&
               password.charAt(28) == '0' &&
               password.charAt(29) == '9' &&
               password.charAt(30) == '2' &&
               password.charAt(31) == 'e'

```

- en este archivo vamos a aplicar el comando sort para ordenarlo, awk para que nos muestre la tercer columna de cada linea, el comando tr -d para quitar las comillas y para quitar el salto de linea.
- concatenamos estos comandos con pipe line y obtenemos la bandera
``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ cat txt.txt | sort | awk '{print($3)}' | tr -d  "'" | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_75092e 
```

picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}
### Notas adicionales:



### Referencias:
