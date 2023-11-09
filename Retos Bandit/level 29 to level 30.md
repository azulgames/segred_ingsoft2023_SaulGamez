## Level  29 to level 30

### Objetivos 
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit29
pasword: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
Port: 2220
```

 Conexión:
```
ssh bandit29@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit29@bandit:~$ mktemp -d
/tmp/tmp.MQ1n1wFK11
bandit29@bandit:~$ cd /tmp/tmp.MQ1n1wFK11
bandit29@bandit:/tmp/tmp.MQ1n1wFK11$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tmp.MQ1n1wFK11$ ls
repo
bandit29@bandit:/tmp/tmp.MQ1n1wFK11$ cd repo
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ ls -la
total 16
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 28 23:42 .
drwx------ 3 bandit29 bandit29 4096 Sep 28 23:42 ..
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 28 23:42 .git
-rw-rw-r-- 1 bandit29 bandit29  131 Sep 28 23:42 README.md
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ cat readme.md
cat: readme.md: No such file or directory
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git log
commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

commit 1a57cf10158f133c4f40ff82251f605a7618631d
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git branch
* master
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git show remotes/origin/HEAD
commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

diff --git a/README.md b/README.md
index 2da2f39..1af21d3 100644
--- a/README.md
+++ b/README.md
@@ -3,6 +3,6 @@ Some notes for bandit30 of bandit.

 ## credentials

-- username: bandit29
+- username: bandit30
 - password: <no passwords in production!>

bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git show remotes/origin/dev
commit 13e735685c73e5e396252074f2dca2e415fbcc98 (origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials

 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git checkout remotes/origin/dev
Note: switching to 'remotes/origin/dev'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 13e7356 add data needed for development
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git log
commit 13e735685c73e5e396252074f2dca2e415fbcc98 (HEAD, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add data needed for development

commit 8caf551dba9f9e39bc8ea4163de7902e6fa85f3a
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add gif2ascii

commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (origin/master, origin/HEAD, master)
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    fix username

commit 1a57cf10158f133c4f40ff82251f605a7618631d
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git branch
* (HEAD detached at origin/dev)
  master
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git show 1a57cf10158f133c4f40ff82251f605a7618631d
commit 1a57cf10158f133c4f40ff82251f605a7618631d
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    initial commit of README.md

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..2da2f39
--- /dev/null
+++ b/README.md
@@ -0,0 +1,8 @@
+# Bandit Notes
+Some notes for bandit30 of bandit.
+
+## credentials
+
+- username: bandit29
+- password: <no passwords in production!>
+
bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$ git show 13e735685c73e5e396252074f2dca2e415fbcc98
commit 13e735685c73e5e396252074f2dca2e415fbcc98 (HEAD, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:40 2023 +0000

    add data needed for development

diff --git a/README.md b/README.md
index 1af21d3..a4b1cf1 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
 ## credentials

 - username: bandit30
-- password: <no passwords in production!>
+- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/tmp.MQ1n1wFK11/repo$
```

### Notas adicionales:
git clone : clonamos el repositorio a la carpeta temporal
git log: nos dice la rama y e informacion del ultimo comit
git branch -a: muestra las ramas del repositorio
git show: nos da informacion de cualquier elemento de git
git chechout: nos cambia a la branch que le especifiquemos.



### Referencias:
https://www.hostinger.mx/tutoriales/comandos-de-git