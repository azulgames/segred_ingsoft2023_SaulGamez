## ReadMyCert

### Objetivos 
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/425/readmycert.csr).

### Pistas
1. Download the certificate signing request and try to read it.

### Solución 

``` bash
┌──(kali㉿kali)-[~/Retos]
└─$ cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF82OTNm
N2MwM30xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAPp+XuDB3ZkmrkvAsgtjP+mjIcYDWfptuZsJieu6eRl39wl4Sg38
+/OfY24LV9sNmgKyTGvpmCaUoZMYkvkulYSoFzE0xqPBo6kruLEyIvqqpAFqRH2b
mierLT6RcKgJHYr/Vt6SwP8NCCawCrvhQ4NZcuB49Hr/2AiGHzmf86/lG/c+lhmH
gyqPb1kDghsVxi/GNs9i7AgniZikqT8OTp0INmmCgZtJn1Jo615Iu/tFiC8Sfhhg
QHmTDLjgx1oP1kvZV2PE5UUN/oC05Zup8f31LksXZwpazZKwYC/LbN96HdqgVQ9K
S8e/4I7MJQmPmLIsLp3sdL2FiDGML3smAi0CAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAOxSR8Fs
Tdjfu9e0vRNqKWd09ISmYDQc3qnSbLRlYZyMK4pguALq310h/1nNgURWESbNJPOp
FkBWG0XWhWyWP7rTqxo/pk9AKx0TNbHDrS6KiBnKPq0mxjPZsH1L7wNYDc5OANDl
btvn3zT7lMms6z1qM7xUWXR76n2xL/81cdF725nBZ00mWmPW0S1pSmA4EEHCEgNW
0vWQqsIDki3gYc4NCm8OHjx79kcwE+ksyc6vHgMOwsYoOFJnyayhl15oN/3x7hW3
G1xovPupABpfOSNOcTwbgfrfjUDOLx/wirvj9L1N5EGDh4FOLaRZDs+tMrimGBBS
zGU13BnykmQ5jOQ=
-----END CERTIFICATE REQUEST-----

```

- introducimos el certificado en la siguiente pagina:
https://www.sslshopper.com/csr-decoder.html

- nos da la información del certificado
```
CSR Information:

Common Name: picoCTF{read_mycert_693f7c03}

Key Size: 2048 bit
```

picoCTF{read_mycert_693f7c03}

### Notas adicionales:

### Referencias: