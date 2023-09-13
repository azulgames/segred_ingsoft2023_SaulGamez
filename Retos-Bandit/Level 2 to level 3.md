## Level 2 to level 3

### Objetivos 
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit2
pasword: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
Port: 2220
```

 Conexión:
```
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```

### Notas adicionales:
cuando tenemos un archivo con espacios en su nombre, para ver el contenido tenemos que poner el nombre completo del archivo entre comillas

### Referencias:
https://linuxhandbook.com/filename-spaces-linux/