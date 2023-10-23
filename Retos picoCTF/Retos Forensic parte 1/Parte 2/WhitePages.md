## WhitePages
### Objetivos 
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) is all blank!

### Pistas
none

### Solución 


- descargamos el archivo, lo leemos y nos encontramos solo espacios en blanco.
- hacemos un analisis hexadecimal
``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ cat whitepages.txt 
                                                                                                                                          
┌──(kali㉿kali)-[~/Retos]
└─$ xxd whitepages.txt 
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
 ```

- nos damos cuenta que hay un mensaje en binario oculto en el archivo, donde los 'e280 83' representan 1 y los '20' un cero.
- hacemos un script en python para transformar este mensaje.

- instalamos pwntools para editar mas facilmente el texto.
``` bash                                                              
┌──(kali㉿kali)-[~/Retos]
└─$ sudo python3 -m pip install pwntools 

┌──(kali㉿kali)-[~/Retos]
└─$ nano exp.py
```

script:
```
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)
```

- ejecutamos el script
```
┌──(kali㉿kali)-[~/Retos]
└─$ python3 exp.py

b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}\n\t\t'
```

picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}

### Notas adicionales:

### Referencias:

