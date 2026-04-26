# Nombre del reto
>Strings it

---
# Descripción
>Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/a35dc624cfda858ed12a4bce57f832dad3b433bad6cde2b98e25fae4bc8ff760/strings) without running it?

---
# Solución
# Solución 1: Función strings con grep
Para empezar, intentemos con strings para recuperar el documento del archivo, lo cual nos llena la pantalla de datos que no tienen mucha importancia, podemos intentar con grep para saber si el documento tiene la flag ahí mismo.

```bash
mv -i strings Strings
strings Strings | grep picoCTF{
```
Esto nos resulta en la flag, pues grep recupera las líneas que coinciden con el patrón de texto.

---
# Flag del reto
>picoCTF{5tRIng5_1T_60eA8fdA}

---
# Notas adicionales

---
# Referencias

Se requirió investigar acerca del comando [strings](https://chatgpt.com/share/698a84f5-71e4-800b-8ca5-a2dbd9b5893d) con ayuda de la IA.