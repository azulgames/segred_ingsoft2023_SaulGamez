## Level 3 to level 4

### Objetivos 
The password for the next level is stored in a hidden file in the **inhere** directory.

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit3
pasword: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
Port: 2220
```

 Conexión:
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Apr 23 18:04 .
drwxr-xr-x 3 root    root    4096 Apr 23 18:04 ..
-rw-r----- 1 bandit4 bandit3   33 Apr 23 18:04 .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

```

### Notas adicionales:

con el comando ls -a mostramos todos los archivos incluyendo los ocultos.
tambien con el comando ls -la mostramos de manera extendida los archivos.

### Referencias:
https://www.sysadmit.com/2016/03/linux-ver-archivos-ocultos.html#:~:text=Para%20ver%20los%20archivos%20y,%22a%22%20al%20comando%20ls.&text=Tambi%C3%A9n%20es%20posible%20utilizar%20el%20comando%20find.&text=*%20El%20parametro%20%2Dtype%20f%2C,type%20d%2C%20nos%20buscar%C3%A1%20directorios.