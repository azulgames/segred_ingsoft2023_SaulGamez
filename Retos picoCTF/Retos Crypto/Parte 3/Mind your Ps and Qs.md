## Mind your Ps and Qs

### Objetivos 
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)
### Pistas
1. Bits are expensive, I used only a little bit over 100 to save money

### Solución 

- factorizamos n en la siguente pagina:
http://factordb.com/index.php?query=631371953793368771804570727896887140714495090919073481680274581226742748040342637

- obtenemos los siguientes valores
= [1461849912200000206276283741896701133693](http://factordb.com/index.php?id=1100000002524294866)<40> 
[431899300006243611356963607089521499045809](http://factordb.com/index.php?id=1100000002524294865)<42>

``` bash
┌──(kali㉿kali)-[/opt]
└─$ python3

Python 3.11.5 (main, Aug 29 2023, 15:31:31) [GCC 13.2.0] on linux
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> e = 65537
>>> p = 1461849912200000206276283741896701133693
>>> q =  431899300006243611356963607089521499045809
>>> n = p * q
>>> n
631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> pow(c,d,n)
13016382529449106065927291425342535437996222135352905256639647889241102700065917
>>> m = pow(c,d,n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_55304594}'
>>> 

```

picoCTF{sma11_N_n0_g0od_55304594}
### Notas adicionales:


c - texto cifrado
m - mensaje texto plano
p - primo 1
q - primo 2
n - modulo
tn- totient n (euler)
e - exponente (llave publica)
d - llave privada

n = p * q
tn = (p-1)*(q-1)
d = e mod inv tn / inverse(e, tn)

encriptar	: c = m^e mod n / pow(m,e,n)
desencriptar	: m = c^e mod n / pow(c,d,n)

### Referencias:
RSA: https://simple.wikipedia.org/wiki/RSA_algorithm