## Irish-Name-Repo 3 

### Objetivos 
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

### Pistas
Seems like the password is encrypted.

### Solución 
- activamos el campo de debug desde las herramientas de desarrollador para ver las sentencias sql.
- al introducir una contraseña nos damos cuenta que los caracteres están siendo encriptados en rot13
- para solucionar este reto, tomaremos nuestra inyeccion sql y la rotaremos a rot13 antes de introducirla al campo. esto provoca que al ingresar nuevamente, la contraseña vuelva al estado inicial y sea efectiva nuestra inyeccion.

``` bash
password: ' be 1==1;
SQL query: SELECT * FROM admin where password = '' or 1==1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}
```

### Notas adicionales:



### Referencias:
sql injection: https://www.imperva.com/learn/application-security/sql-injection-sqli/#:~:text=SQL%20injection%2C%20also%20known%20as,not%20intended%20to%20be%20displayed.

rot13: https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBvciAxPT0xOw