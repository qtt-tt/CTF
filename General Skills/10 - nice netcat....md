# Nombre del reto
>nice netcat...

---
# Descripción
>There is a nice program that you can talk to by using this command in a shell:
>
>$ nc wily-courier.picoctf.net 58401, but it doesn't speak English...

---
# Solución
## Solución 1: Uso del comando awk
En este reto, al conectarse al servicio nos manda un conjunto de números en varias líneas individuales, por lo que aquí debemos entrar a usar un procesador de textos como lo es awk.
Este comando nos permite procesar líneas que llegan una por una, en este caso, se usó la siguiente sintaxis:
```bash
nc wily-courier.picoctf.net 58401 | awk '{printf "%c", $1}'
```
Este código lo que hace es conectarse a cierto servicio a través de dicho puerto, de modo que lo que, su salida (que son varias líneas) se le manda a awk para que imprima cada caracter junto (sin salto de línea) pidiendo su valor ASCII (con el %c), esto nos resulta en la flag.

---
# Flag del reto
>picoCTF{g00d_k1tty!_n1c3_k1tty!_f7a6e}

---
# Notas adicionales

---
# Referencias

