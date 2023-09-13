### level 16 to level 17

### Objetivos 
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit16
pasword: JQttfApK4SeyHwDlI9SXGR50qclOAil1
Port: 2220
```

 Conexión:
```
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
nmap localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2023-09-13 16:19 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

bandit16@bandit:~$ openssl s_client -connect localhost:31790
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: EB9969E10FC87E1165D8B1A6D0B40BD3BA6F45F8D26477CA59ECC7BD6191CC63
    Session-ID-ctx:
    Resumption PSK: 6B29566B31BCDCB87497A51A3005ACE5C23E06D7B8B779838CE85A9613201E91ABEA80734F4BD6EB6712F14D19C4382A
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 8a 53 79 53 f7 5d bc c9-dd 02 bc 88 5e 20 c6 eb   .SyS.]......^ ..
    0010 - ea 69 67 f3 01 7a 96 19-dd 3b b3 e6 34 bd ad b9   .ig..z...;..4...
    0020 - 8e b3 48 7e 01 fe a9 cb-5d 23 fe 9c 39 16 c8 fa   ..H~....]#..9...
    0030 - 47 c4 ba 00 d1 74 3f 76-84 ce db da e6 a9 6b 46   G....t?v......kF
    0040 - 88 f5 d8 18 60 ce d8 0a-d0 e4 25 e9 50 5d 55 87   ....`.....%.P]U.
    0050 - ed ff 70 4c 79 72 b3 b0-b8 df 2e e5 81 48 49 ee   ..pLyr.......HI.
    0060 - 8d 92 b4 eb 1c 18 d3 fb-84 00 70 60 64 4c 84 a0   ..........p`dL..
    0070 - b5 35 61 f0 21 ad 85 72-7a fb 8a bc 16 b6 81 69   .5a.!..rz......i
    0080 - b7 10 ec 66 a6 29 f9 3d-b4 f8 b7 52 14 4e 6e d5   ...f.).=...R.Nn.
    0090 - 8b 6c 1f d3 d8 ce 34 a3-34 1d 64 91 9f 04 53 93   .l....4.4.d...S.
    00a0 - 78 92 64 de 73 38 a9 5e-6e 71 5e 9b c8 5d d0 40   x.d.s8.^nq^..].@
    00b0 - f8 17 32 13 f8 a7 f2 d0-ae 05 94 59 0d 97 4d 7c   ..2........Y..M|
    00c0 - 97 91 b7 3f d9 b6 a9 4a-0e b3 aa a9 d9 9e 9e 1c   ...?...J........

    Start Time: 1694622324
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
```

### Notas adicionales:
nmap localhost escanea los puertos más comunes
nmap localhost -p 31000-32000 escanea los puertos en ese rango dado
openssl s_client -connect localhost:31046
pregunta si el puerto habla en ssl
### Referencias:
