### Level 7 to level 8

### Objetivos 
The password for the next level is stored in the file **data.txt** next to the word **millionth**
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit7
pasword: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
Port: 2220
```

 Conexión:
```
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ wc data.txt
  98567  197133 4184396 data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
bandit7@bandit:~$

```

### Notas adicionales:

wc cuenta el numero de lineas y caracteres y bytes de un archivo
grep busca patrones en cada archivo
### Referencias:
https://docs.oracle.com/cd/E19620-01/805-7644/6j76klop3/index.html#:~:text=grep%20se%20utiliza%20muy%20a,de%20comunicaci%C3%B3n%20es%20%22%20%7C%20%22.