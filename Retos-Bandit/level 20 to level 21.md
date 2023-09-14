## Level 20 to level 21

### Objetivos 
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit20
pasword: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Port: 2220
```

 Conexión:
```
ssh bandit20@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit20@bandit:~$ nc -lnvp 5050 <<< "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" &
[1] 2878975
bandit20@bandit:~$ Listening on 0.0.0.0 5050

bandit20@bandit:~$ jobs
[1]+  Running                 nc -lnvp 5050 <<< "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" &
bandit20@bandit:~$ ./suconnect 5050
Connection received on 127.0.0.1 49050
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+  Done                    nc -lnvp 5050 <<< "VxCazJaVykI6W36BkBU0mJTCM8rR95XT"
bandit20@bandit:~$
```

### Notas adicionales:
nc -lnvp 5050 <<< "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" &
ahi abrimos un puerto y lo dejamos a la escucha en segudo plano


### Referencias:
