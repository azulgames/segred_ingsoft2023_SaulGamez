### Level 11 to level 12

### Objetivos 
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit11
pasword: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
Port: 2220
```

 Conexión:
```
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```

### Notas adicionales:
rot13 desplaza las letras 13 veces en el abecedario
tr es un comando que recorre las letras segun le indiques

### Referencias:
[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)