## Level 31 to level 32
### Objetivos 
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit31
pasword: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
Port: 2220
```

 Conexión:
```
ssh bandit31@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ ls
README.md

bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ git branch
* master

bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ ls
key.txt  README.md
bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ cat key.txt 
May I come in?

bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ git add key.txt
The following paths are ignored by one of your .gitignore files:
key.txt
hint: Use -f if you really want to add them.
hint: Turn this message off by running
hint: "git config advice.addIgnoredFile false"

bandit31@bandit:/tmp/tmp.Xu97xjd6x1/repo$ git add -f key.txt
bandit31@bandit:/tmp/tmp.Xu97xjd6x1/repo$ git commit -m "update key.txt file"
[master fedf826] update key.txt file
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.fl58UHGnqV/repo$ git push
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 330 bytes | 330.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
```


### Notas adicionales:

git add -f agrega los archivos al git de manera forzosa

### Referencias:
https://www.atlassian.com/git/tutorials/saving-changes