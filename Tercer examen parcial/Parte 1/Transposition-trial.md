## Transposition-trial

### Objetivos 
plit the message up into blocks of 3 and see how the first block is scrambled

### Pistas
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/191/message.txt).

### Solución 

- descargamos el archivo y nos damos cuenta que hay bloques de tres rotados, así que hacemos un script en Python para revertir este proceso.

```

```

- python script:

``` python
with open("message.txt") as filp:
	contenido = filp.read()

flag = []
for i in range(0, len(contenido), 3):
	bloque = contenido[i : i + 3]

	a, b, c = bloque
	flag.append(c + a + b)

flag = "".join(flag).split()[-1]
print(flag)
```

```
┌──(kali㉿kali)-[~/Retos]
└─$ nano flag                              

┌──(kali㉿kali)-[~/Retos]
└─$ python py.py -> flag.txt                                 

┌──(kali㉿kali)-[~/Retos]
└─$ cat flag.txt  
picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}
```
### Notas adicionales:

### Referencias:
