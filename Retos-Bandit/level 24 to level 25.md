## Level 24 to level 25

### Objetivos 
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit24
pasword: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
Port: 2220
```

 Conexión:
```
ssh bandit24@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit24@bandit:~$ nc -v localhost 30002 
Connection to localhost (127.0.0.1) 30002 port [tcp/*] succeeded!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 123 
Wrong! Please enter the correct pincode. Try again. VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 987 
Wrong! Please enter the correct pincode. Try again. 
^C 
bandit24@bandit:~$ for i in {0000..0003}; do echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i ; done UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0000 UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0001 UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0002 UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0003 bandit24@bandit:~$ 
for i in {0000..9999}; 
do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v 
Wrong I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space. 
Correct! The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d Exiting.
```

### Notas adicionales:

nos conectamos a un puerto y nos comunicamos con el demonio
podemos hacer un ciclo para probar combinaciones de números.

### Referencias:
