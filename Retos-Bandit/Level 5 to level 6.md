## Level 5 to level 6

### Objetivos 

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit5
pasword: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
Port: 2220
```

 Conexión:
```
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit5@bandit:~$ bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Apr 23 18:04 .
drwxr-xr-x  3 root root    4096 Apr 23 18:04 ..
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere00
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere01
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere02
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere03
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere04
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere05
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere06
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere07
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere08
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere09
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere10
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere11
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere12
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere13
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere14
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere15
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere16
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere17
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere18
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere19
bandit5@bandit:~/inhere$ find . -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

### Notas adicionales:

el comando find nos ayuda a encontrar archivos con caracteristicas especificar que podemos especificar en los parametros:
- readable: que se pueda leer.
- type f: que sea de tipo archivo.
- size: que sea del tamaño especificado. 

### Referencias:
https://www.ionos.es/digitalguide/servidores/configuracion/comando-linux-find/#:~:text=El%20comando%20find%20de%20Linux%20es%20una%20herramienta%20precisa%20para,todas%20las%20distribuciones%20de%20Linux.