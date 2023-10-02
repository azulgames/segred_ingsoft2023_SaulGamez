## Level 23 to level 24

### Objetivos 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit23
pasword: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
Port: 2220
```

 Conexión:
```
ssh bandit23@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit23@bandit:~$ ls /etc/cron.d 
cronjob_bandit15_root cronjob_bandit22 cronjob_bandit24 e2scrub_all sysstat cronjob_bandit17_root cronjob_bandit23 cronjob_bandit25_root otw-tmp-dir 
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24 @reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null * * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh 

#!/bin/bash 

myname=$(whoami) 

cd /var/spool/$myname/foo 
echo "Executing and deleting all scripts in /var/spool/$myname/foo:" 
for i in * .*;
do 
	if [ "$i" != "." -a "$i" != ".." ]; 
	then 
		echo "Handling $i" 
		owner="$(stat --format "%U" ./$i)" 
		if [ "${owner}" = "bandit23" ]; 
			then timeout -s 9 60 ./$i 
		fi 
		rm -f ./$i 
	fi 
done 

bandit23@bandit:~$ mkdir /tmp/kd 
bandit23@bandit:~$ cd /tmp/kd 
bandit23@bandit:/tmp/kd$ echo "cat /etc/bandit_pass/bandit24 > /tmp/kd/password" > script.sh 
bandit23@bandit:/tmp/kd$ cat script.sh cat /etc/bandit_pass/bandit24 > /tmp/kd/password bandit23@bandit:/tmp/kd$ chmod +x script.sh bandit23@bandit:/tmp/kd$ touch password 
bandit23@bandit:/tmp/kd$ chmod 666 password bandit23@bandit:/tmp/kd$ ls –la total 92 drwxrwxr-x 2 bandit23 bandit23 4096 Sep 4 01:51 .
drwxrwx-wt 1957 root root 81920 Sep 4 01:51 ..
-rw-rw-rw- 1 bandit23 bandit23 0 Sep 4 01:51 password 
-rwxrwxr-x 1 bandit23 bandit23 49 Sep 4 01:50 script.sh
bandit23@bandit:/tmp/kd$ cp script.sh /var/spool/bandit24/foo bandit23@bandit:/tmp/kd$ ls -la 
total 92 
drwxrwxr-x 2 bandit23 bandit23 4096 Sep 4 01:51 . 
drwxrwx-wt 1957 root root 81920 Sep 4 01:53 .. 
-rw-rw-rw- 1 bandit23 bandit23 0 Sep 4 01:51 password 
-rwxrwxr-x 1 bandit23 bandit23 49 Sep 4 01:50 script.sh 
bandit23@bandit:/tmp/kd$ date Sun Sep 4 01:54:12 AM UTC 2022 bandit23@bandit:/tmp/kd$ ls -la 
total 96
drwxrwxr-x 2 bandit23 bandit23 4096 Sep 4 01:51 . 
drwxrwx-wt 1957 root root 81920 Sep 4 01:53 .. 
-rw-rw-rw- 1 bandit23 bandit23 33 Sep 4 01:54 password 
-rwxrwxr-x 1 bandit23 bandit23 49 Sep 4 01:50 script.sh bandit23@bandit:/tmp/kd$ cat password VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

### Notas adicionales:

revisaremos el cron para ver los scripts programados, vamos a mandar el password a una carpeta que nosotros creamos y le daremos permisos
para que el script se ejectute, y obtenemos la contraseña
### Referencias:
