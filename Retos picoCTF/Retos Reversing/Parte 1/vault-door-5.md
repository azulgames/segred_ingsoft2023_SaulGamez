## vault-door-5

### Objetivos 
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)

### Pistas
1. You may find an encoder/decoder tool helpful, such as https://encoding.tools/
2. Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like
### Solución 

- Extraemos la parte de la validación del código java que está decodificada y le quitamos los espacios, comillas y saltos de linea.
``` bash
JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0
```

- este resultado lo traducimos de base64 en la siguiente pagina:
 masterChef base64: https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm1KVFkySlRjeUpUTXdKVFprSlRWbUpUWXlKVFl4SlRNMUpUWTFKVFZtSlRNMkpUTTBKVFZtSlRZMUpUTXpKVE14SlRNMUpUTXlKVFl5SlRZMkpUTTAi

- le damos a la barita mágica para ver la bandera

picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}
### Notas adicionales:

### Referencias:
