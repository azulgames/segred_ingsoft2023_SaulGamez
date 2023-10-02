## Level x to level x

### Objetivos 
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit19
pasword: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Port: 2220
```

 Conexión:
```
ssh bandit19@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit19@bandit:~$ bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ./bandit20-do
Run a command as another user.
  Example: ./bandit20-do id
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$
```

### Notas adicionales:

./bandit20-do
a través de ese archivo simulamos ser otro usuario para ejecutar un comando
### Referencias:
https://en.wikipedia.org/wiki/Setuid