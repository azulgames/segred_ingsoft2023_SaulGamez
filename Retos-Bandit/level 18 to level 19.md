## Level 18 to level 19

### Objetivos 
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit18
pasword: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
Port: 2220
```

 Conexión:
```
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

### Solución 

como el servidor nos saca al entrar ejecutamos una linea de codigo al entrar

``` bash
C:\Users\saula>ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
````

Solucion 2 abrir una subterminal antes de que nos saque
```
C:\Users\saula>ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
Permission denied, please try again.
bandit18@bandit.labs.overthewire.org's password:
ls
readme
whoami
bandit18
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

### Notas adicionales:

como el servidor nos saca al entrar ejecutamos una linea de codigo al entrar

### Referencias:
https://ubunlog.com/bashrc-modifica-prompt-bash/