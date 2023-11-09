## Level 6 to level 7

### Objetivos 
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit6
pasword: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
Port: 2220
```

 Conexión:
```
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash

bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:~$

```

### Notas adicionales:

find: busca archivos
	/ desde la raiz
	-user especificamos el usuario
	-group especificamos a que grupo pertenece
	-size especificamos el tamaño
	2>/dev/null mandamos los errores a null (no los muestra)

### Referencias:
https://man7.org/linux/man-pages/man1/find.1.html