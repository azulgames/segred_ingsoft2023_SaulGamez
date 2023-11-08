## titulo

### Objetivos 
What does asm3(0xd73346ed,0xd48672ae,0xd3c8b139) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S)

### Pistas
1. more(?) [registers](https://wiki.skullsecurity.org/index.php?title=Registers)

### Solución 

- pegamos el código proporcionado en: https://carlosrafaelgn.com.br/Asm86/
- agregamos los 3 elementos a la pila y llamamos a asm3
- seguimos al ejecucion por pasos con la ventana de registro activada
- el ultimo registro en EAX será el resultado
``` bash
start:
	push 0xd3c8b139
	push 0xd48672ae
	push 0xd73346ed
	call asm3


asm3:
	push   ebp
	mov    ebp,esp
	xor    eax,eax
	mov    ah,BYTE PTR [ebp+0xa]
	shl    ax,0x10
	sub    al,BYTE PTR [ebp+0xc]
	add    ah,BYTE PTR [ebp+0xd]
	xor    ax,WORD PTR [ebp+0x10]
	nop
	pop    ebp
	ret   
```

EAX: 0x0000C36B

flag: 0xC36B

### Notas adicionales:

Operaciones lenguaje ensamblador:

- **add.** Instruye al procesador para que sume dos operandos y almacene el resultado.
- **mov.** Es una instrucción común en varios lenguajes ensambladores, sirve para mover datos o registros de un sitio a otro.
- **mul.** Da instrucciones al procesador de realizar la multiplicación de dos operandos, cumpliendo previamente con ciertas condiciones.
- **and.** Es la instrucción necesaria para utilizar el operador lógico ‘y’ en lenguaje ensamblador.
- **cmp.** Esta instrucción **resta el operando fuente al operando destino pero sin que éste almacene el resultado de la operación**, solo se afecta el estado de las banderas.
- **jg:** Salta si es más grande o salta si no es menor o igual.

### Referencias:
