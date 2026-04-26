# Nombre del reto
>Glitch Cat

---
# Descripción
>Our flag printing service has started glitching!
>
>$ nc saturn.picoctf.net 62691

---
# Solución
## Solución 1: obtención de cadena formateada en Python
En la descripción nos indica que nos conectemos a un servicio a través de cierto puerto. Dicha conexión nos arroja una cadena rara la cual se ve de la siguiente manera:
*'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'*
Si la analizamos un poco, podemos ver una función chr() la cual es usada en Python para obtener caracteres de ciertos valores. Por lo que al ingresarla e imprimirla en Python nos resulta la flag.
```python
cadena = 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
print(cadena)
```

---
# Flag del reto
>picoCTF{gl17ch_m3_n07_a4392d2e}

---
# Notas adicionales

---
# Referencias

