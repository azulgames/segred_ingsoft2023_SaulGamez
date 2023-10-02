## Level  30 to level 31

### Objetivos 
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit30
pasword: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
Port: 2220
```

 Conexión:
```
ssh bandit30@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit30@bandit:/tmp/tmp.LylEaKxn4F$ cd repo/
bandit30@bandit:/tmp/tmp.LylEaKxn4F/repo$ ls
README.md
bandit30@bandit:/tmp/tmp.LylEaKxn4F/repo$ cat README.md 
just an epmty file... muahaha

bandit30@bandit:/tmp/tmp.LylEaKxn4F/repo$ git log
commit cf552c166d78421e64ddf52f850e680075d216e1 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:13 2023 +0000
    initial commit of README.md
    
bandit30@bandit:/tmp/tmp.LylEaKxn4F/repo$ git branch
* master
bandit30@bandit:/tmp/tmp.LylEaKxn4F/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  
bandit30@bandit:/tmp/tmp.LylEaKxn4F/repo$ git show-ref
cf552c166d78421e64ddf52f850e680075d216e1 refs/heads/master
cf552c166d78421e64ddf52f850e680075d216e1 refs/remotes/origin/HEAD
cf552c166d78421e64ddf52f850e680075d216e1 refs/remotes/origin/master
831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret
bandit30@bandit:/tmp/tmp.X0b44vxUoy/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/tmp.X0b44vxUoy/repo$ 831aac2e2341f009e40e46392a4f5dd318483019
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

### Notas adicionales:
git tag: muesta las etiquetas del repositorio
git show-ref: muestra las etiquetas y referencias en el repositorio local

### Referencias:
https://www.atlassian.com/es/git/tutorials/inspecting-a-repository/git-tag
https://git-scm.com/docs/git-show-ref