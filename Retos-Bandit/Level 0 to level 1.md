# Level 0 to level 1

### Objetivos 
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
### Datos de acceso al nivel 
``` bash
user: bandit0
password: bandit0
```
### Solución 
``` bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

### Notas adicionales:

comandos utilizados:
- ls: muestra los archivos 
- cat: muestra el contenido de un archivo
### Referencias:
