## Mr-Worldwide

### Objetivos 
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

### Pistas
None

### Solución 
- tenemos la siguiente bandera, lo que parecen ser cordenadas de gps

picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}

si vamos a cada ubicacion en google maps podemos ver los caracteres que conforman a la bandera en la primera letra de cada ciudad


(35.028309, 135.753082) Kyoto, Japan
(46.469391, 30.740883) Odessa, Ukraine
(39.758949, -84.191605) Dayton, United States
(41.015137, 28.979530) Istanbul, Turkey
(24.466667, 54.366669) Abu Dhabi, UAE
(3.140853, 101.693207) Kuala Lumpur, Malaysia
(9.005401, 38.763611) Addis Ababa, Ethiopia
(-3.989038, -79.203560) Loja, Ecuador
(52.377956, 4.897070) Amsterdam, Netherlands
(41.085651, -73.858467) Sleepy Hollow, USA
(57.790001, -152.407227) Kodiak, United State
(31.205753, 29.924526) Alexandria, Egypt

K O D I A K A L A S K A

- separamos ambas palabras y la ajustamos al formato:

picoCTF{KODIAK_ALASKA}

### Notas adicionales:

### Referencias:
