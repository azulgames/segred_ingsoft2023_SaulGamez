## Matryoshka doll
### Objetivos 
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg)

### Pistas
1. Wait, you can hide files inside files? But how do you find them?

### Solución 

- nos damos cuenta que la imagen tiene bytes extra, y la descomprimimos con unzip
- nos encontraremos una imagen muy parecida, con bytes extra, y también la descomprimimos. hacemos esto hasta que nos encontramos la bandera.

``` bash
 
 ┌──(kali㉿kali)-[~/Retos]
└─$ unzip dolls.jpg 
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     
                                                                                 
┌──(kali㉿kali)-[~/Retos]
└─$ ls -la
total 680
drwxr-xr-x  4 kali kali  28672 Oct 23 23:04 .
drwx------ 21 kali kali   4096 Oct 23 18:06 ..
drwxr-xr-x  2 kali kali   4096 Oct 23 23:04 base_images
-rw-r--r--  1 kali kali 651634 Mar 15  2021 dolls.jpg
drwxrwxrwx  5 kali kali   4096 Oct 18 12:59 sstv
                                                                                
  
┌──(kali㉿kali)-[~/Retos]
└─$ cd base_images 
                                                                       
┌──(kali㉿kali)-[~/Retos/base_images]
└─$ ls -la
total 408
drwxr-xr-x 2 kali kali   4096 Oct 23 23:04 .
drwxr-xr-x 4 kali kali  28672 Oct 23 23:04 ..
-rw-r--r-- 1 kali kali 383938 Mar 15  2021 2_c.jpg
                                                                      
┌──(kali㉿kali)-[~/Retos/base_images]
└─$ unzip 2_c.jpg  
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     
                                                                  
┌──(kali㉿kali)-[~/Retos/base_images]
└─$ ls -la
total 412
drwxr-xr-x 3 kali kali   4096 Oct 23 23:05 .
drwxr-xr-x 4 kali kali  28672 Oct 23 23:04 ..
-rw-r--r-- 1 kali kali 383938 Mar 15  2021 2_c.jpg
drwxr-xr-x 2 kali kali   4096 Oct 23 23:05 base_images
                                                                                
┌──(kali㉿kali)-[~/Retos/base_images]
└─$ cd base_images 
                                                                              
┌──(kali㉿kali)-[~/Retos/base_images/base_images]
└─$ ls -la 
total 208
drwxr-xr-x 2 kali kali   4096 Oct 23 23:05 .
drwxr-xr-x 3 kali kali   4096 Oct 23 23:05 ..
-rw-r--r-- 1 kali kali 201445 Mar 15  2021 3_c.jpg
                         
┌──(kali㉿kali)-[~/Retos/base_images/base_images]
└─$ unzip 3_c.jpg
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     
                                                                               
┌──(kali㉿kali)-[~/Retos/base_images/base_images]
└─$ cd base_images 
                                                                             
┌──(kali㉿kali)-[~/Retos/base_images/base_images/base_images]
└─$ unzip 4_c.jpg
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: flag.txt                
                                                                            
┌──(kali㉿kali)-[~/Retos/base_images/base_images/base_images]
└─$ ls -la
total 92
drwxr-xr-x 2 kali kali  4096 Oct 23 23:06 .
drwxr-xr-x 3 kali kali  4096 Oct 23 23:06 ..
-rw-r--r-- 1 kali kali 79807 Mar 15  2021 4_c.jpg
-rw-r--r-- 1 kali kali    81 Mar 15  2021 flag.txt
                                                                              
┌──(kali㉿kali)-[~/Retos/base_images/base_images/base_images]
└─$ cat flag.txt      
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b} 
```

picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
### Notas adicionales:

herramientas que nos pueden ayudar a descomprimir un archivo oculto dentro de otro:
- unzip
- binwalk
### Referencias:
