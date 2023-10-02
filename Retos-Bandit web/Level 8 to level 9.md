## Level 8 to level 9

### Objetivos 
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit9
pasword: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Port: 2220
```

 Conexión:
```
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit8@bandit:~$ bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ wc data.txt
 1001  1001 33033 data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$
```

### Notas adicionales:

| el pipe redirecciona la salida de un comando a la entrada de otro

### Referencias:
https://www.ionos.es/digitalguide/servidores/configuracion/pipes-linux/#:~:text=Los%20pipes%20son%20una%20herramienta,otro%20entre%20comandos%2C%20por%20ejemplo.