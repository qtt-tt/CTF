# Nombre del reto
>Tapping

---
# Descripción
>Theres tapping coming in from the wires.
>What's it saying nc fickle-tempest.picoctf.net 65187.

---
# Solución
Encontramos que nos está dando este formato:
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ---.. ....- ---.. ----- .- ..-. ----. -.... }
El cual pertenece a un código morse (pues a fin de cuentas se basa en puntos y guiones), lo podemos meter en un [desencriptador](https://www.dcode.fr/morse-code), cabe recalcar que no nos dará la flag para copiar y pegar, nos dará toda las letras (menos las llaves) pegados, entonces solo nos toca pegar la parte de la flag

---
# Flag del reto
>picoCTF{M0RS3C0D31SFUN8480AF96}

---
# Notas adicionales

---
# Referencias

