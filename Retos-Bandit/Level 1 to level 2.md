# Level 1 to level 2

### Objetivos 
The password for the next level is stored in a file called **-** located in the home directory
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit1
pasword: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
Port: 2220
```

 Conexión:
```
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```

### Notas adicionales:

cuando queremos leer un archivo que se llama "-" debemos especificar la ruta completa del archivo para evitar que se confunda el guion con una introducción de parámetros del comando.

### Referencias:
- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)