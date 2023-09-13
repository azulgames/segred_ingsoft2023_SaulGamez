## Level 15 to level 16

### Objetivos 
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
### Datos de acceso al nivel 

```
Host: bandit.labs.overthewire.org  
user: bandit15
pasword: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Port: 2220
```

 Conexión:
```
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

### Solución 

``` bash
bandit15@bandit:~$ nc -v localhost 30001
Connection to localhost (127.0.0.1) 30001 port [tcp/*] succeeded!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
bandit15@bandit:~$
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep 12 19:28:36 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep 12 19:28:36 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep 12 19:27:36 2023 GMT; NotAfter: Sep 12 19:28:36 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEC45O9TANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTEyMTkyNzM2WhcNMjMwOTEyMTkyODM2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDm
l+M89lI121voS7dkGZ7EZ9U7lMwJDqs2PJdnUxmTCqPD7GFPoHjtWgM2q4oEmRnz
LILu0seqdj4DOHVpljo1Su0pZUIOVp/2o7WZB0OQNw4k1syYI4W0o83GZCLINGfk
Kv+jQT5+F/0/xrPlZ0c4R4v8yoIXYHn1XnXTomUPdCe1STkbfuEluPVsUYtOJLr2
JB1oM56rp614mEHUlKwZombyimmbw3K6lh73mn5rUKPYC6ZKueEhcC9v2WULSpuC
yK4JX3lYuT/I4VvAzTN6sHAsHF8a6Y4ve6WSt5id1MRChhbZbsDE7zGVUEndyneY
4PKZGinfeUcaqBI9/jepAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAF
5+5M/8s5aRTQBNsmau7HRbZp+BEeprujSN+5HFxZWyfOoLlAdXFO9tlbhgyMTZ0S
VN8xQB9Oxm07xC8WUakj6yD004S+7N82Nqy9fznaE3DLVGMzwMht8c2NbByfb+iN
x8MNRcWt4GMCV9jjIbuysE6FWFG5CEzaL4T7jCQldbIQpVVHFdaeHk/TmhD4Z6uj
/8az/n1ZdT40rO+QMU1/p3cPTPIeqrQymrtQAQ3wqsGANqOvzZ0IyLo5zaWnPnZL
bO4Q37dkc8VhiDP/7ok++l/Q0qVOVKR6YbdqyqXIQBw35AlpEGvqdaNpDgI1dCgI
mLiJepQjf3IUv/q/OH59
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9B00403A5E946577E5BFEA64E45A0FAF7431FE7CAAD9D714493805482C85BBD5
    Session-ID-ctx:
    Resumption PSK: 870C36BAE4FDA0A3110F49E7E2D46B43FAA41D9F79825221DEADED745CFFAC876A4827FCC908C33799E8250677C697BC
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ef 3c 60 dd c0 30 4a 16-cc e8 65 95 7d f5 1d 44   .<`..0J...e.}..D
    0010 - 30 0e 99 06 91 1f e2 76-11 8f 0c 19 79 89 1d 58   0......v....y..X
    0020 - 90 34 fa 79 5f 0b e4 d5-b3 32 a5 85 64 3e 5b b5   .4.y_....2..d>[.
    0030 - c9 ba 97 31 2b 0c c5 3c-f7 c3 11 29 d5 9a 6d 5b   ...1+..<...)..m[
    0040 - ae dc e2 c9 ff 5c 7e 36-37 03 f5 5b dc 94 0f 9e   .....\~67..[....
    0050 - f8 c5 8d bb 4b db 5b 53-c4 f1 c8 88 f9 35 c9 bd   ....K.[S.....5..
    0060 - b7 dc 03 0c 7a 76 82 f9-9a dc 6a cf 83 68 51 aa   ....zv....j..hQ.
    0070 - 2e b8 cb 38 71 04 c4 32-b0 ef 32 70 e9 25 ef c0   ...8q..2..2p.%..
    0080 - 4e b5 62 ee 08 bb 58 e0-85 3c 6a 7c f3 3d f5 0c   N.b...X..<j|.=..
    0090 - 19 b1 8e a7 c4 d2 09 21-86 c1 dc f3 67 44 37 a7   .......!....gD7.
    00a0 - 30 d4 61 53 b7 83 5d b8-bb 89 ce 44 c6 dd f9 76   0.aS..]....D...v
    00b0 - 17 ef 55 82 99 9d 77 97-7c 4e ad 60 b1 b5 3e 8c   ..U...w.|N.`..>.
    00c0 - 36 bb 5d 6b 93 5b 31 af-14 32 d9 a8 84 ab e6 b3   6.]k.[1..2......

    Start Time: 1694643806
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 2EE72EBC67201CFB758559CFC431A9E403943930063AE2A9A199D9DE7131DB4C
    Session-ID-ctx:
    Resumption PSK: 05ADCCA728DFEC29FF391A1081B18B49D5F03B9B2C4B44842676A45A3C9DCCC508561716EB854230EBC72DD77BE251E7
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ef 3c 60 dd c0 30 4a 16-cc e8 65 95 7d f5 1d 44   .<`..0J...e.}..D
    0010 - 70 1a ed 09 81 26 26 ef-d7 d2 db e0 f6 98 80 3e   p....&&........>
    0020 - cd 65 f4 a4 c7 93 4e d5-5b df cc 92 08 3a c2 85   .e....N.[....:..
    0030 - 77 f9 6f bc 5d db df 84-7e 4d 2c 7d ad ab d0 75   w.o.]...~M,}...u
    0040 - 26 66 1a 49 69 19 e7 38-ee f8 6a 13 6a 01 e9 43   &f.Ii..8..j.j..C
    0050 - 30 a8 11 f3 f8 04 c4 cb-d9 6d 97 ae 3c 48 01 46   0........m..<H.F
    0060 - b7 9d 37 32 80 8b 5e 0f-9e a2 56 65 c7 b7 5c 99   ..72..^...Ve..\.
    0070 - 71 38 bd 4a 35 eb fe 71-d9 a7 97 06 47 71 e8 c5   q8.J5..q....Gq..
    0080 - d7 cb be f2 40 82 82 b3-a5 22 b7 ad d9 10 26 3a   ....@...."....&:
    0090 - 08 26 b6 1c 7f 14 9c 9f-20 36 fb 57 67 1f 72 45   .&...... 6.Wg.rE
    00a0 - bd 20 02 3c f2 b7 e3 67-43 53 f5 4c 80 54 f3 db   . .<...gCS.L.T..
    00b0 - c9 d3 c0 6a a5 44 cb 93-f7 94 9f d7 4b 48 01 85   ...j.D......KH..
    00c0 - b5 2b 04 b9 11 32 01 e8-26 51 f0 a5 19 eb c6 35   .+...2..&Q.....5

    Start Time: 1694643807
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```

### Notas adicionales:
openssl s_client -connect localhost:30001

openssl lo usamos cuando nos conectamos a un puerto protegido


### Referencias:
https://www.cloudflare.com/es-es/learning/ssl/what-is-https/#:~:text=El%20protocolo%20de%20transferencia%20de,de%20las%20transferencias%20de%20datos.