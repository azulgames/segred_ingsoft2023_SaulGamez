## level 14 to level 15

### Objetivos 
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit14
pasword: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq 
Port: 2220
```

 Conexión:
```
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit14@bandit:~$ nc -v
usage: nc [-46CDdFhklNnrStUuvZz] [-I length] [-i interval] [-M ttl]
          [-m minttl] [-O length] [-P proxy_username] [-p source_port]
          [-q seconds] [-s sourceaddr] [-T keyword] [-V rtable] [-W recvlimit]
          [-w timeout] [-X proxy_protocol] [-x proxy_address[:port]]
          [destination] [port]
bandit14@bandit:~$ nc -v localhost 30000
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```

### Notas adicionales:
nc -v localhost 30000
nc hace conexiones remotas

### Referencias:
https://keepcoding.io/blog/que-es-netcat/#:~:text=Netcat%20es%20una%20herramienta%20de,qu%C3%A9%20servicios%20se%20encuentran%20activos.