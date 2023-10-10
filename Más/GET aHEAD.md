## GET aHEAD

### Objetivos 
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

### Pistas
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses

### Solución 1

- seleccionar un boton de la pagina para que cambie de color
- con ayuda de las herramientas de desarrollador, en la categoria de Network vamos a ubicar el Request que se generó al presionar el boton, vamos a reenviar esta peticion, pero cambiando el metodo de GET o POST a HEAD
- en la respuesta de la petición obtendremos la bandera

picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}

### Solución 1 (Consola)

``` bash
saulgamez-picoctf@webshell:~$ curl -I http://mercury.picoctf.net:28916
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}
Content-type: text/html; charset=UTF-8
```

curl -i: solicitamos a travéz de HEAD
### Notas adicionales:

### Referencias:
HTTP Methods: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods