## Reverse_Cipher

### Objetivos 
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this). Can you reverse the flag.

### Pistas
1. objdump and Gihdra are some tools that could assist with this

### Solución 

- descargamos ambos archivos y los analizamos con Ghidra
- creamos un nuevo proyecto en el que importamos el archivo rev para analizarlo.
- nos vamos a la funcion main y nos damos cuenta que lo que está haciendo es revisar si los caracteres en el codigo son pares o impares para sumarle o restarle un digito.

- creamos un script de python para revertir este proceso en nuestra llave.

Script de python:
``` python
cifrado = open('rev_this','r').read()
print(cifrado)

flag = ''

for i in range(8, len(cifrado)-1):
	if i & 1 == 0:
		flag += chr( ord(cifrado[i]) -5 )
	else:
		flag += chr( ord(cifrado[i]) +2 )

print(flag)
```

- Corremos este código y obtenemos la bandera
``` bash
┌──(kali㉿kali)-[~]
└─$ python3 exp.py
picoCTF{w1{1wq84fb<1>49}
r3v3rs36ad73964
```

picoCTF{r3v3rs36ad73964}

### Notas adicionales:

### Referencias:
