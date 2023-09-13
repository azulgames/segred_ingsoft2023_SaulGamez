## Level 9 to level 10

### Objetivos 
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit9
pasword: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
Port: 2220
```

 Conexión:
```
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit9@bandit:~$ bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ file data.txt
data.txt: data
bandit9@bandit:~$ strings data.txt | grep ==
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
```

### Notas adicionales:

grep busca un patrón

### Referencias:
https://www.freecodecamp.org/espanol/news/grep-command-tutorial-how-to-search-for-a-file-in-linux-and-unix-with-recursive-find/