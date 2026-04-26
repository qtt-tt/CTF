# Nombre del reto
>Wave a flag

---
# Descripción
>Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...[warm](https://challenge-files.picoctf.net/c_wily_courier/89a0e56b3f2697fe5d597b2805202b86693dcb0e04aec062e11fe66edbbd04aa/warm)

---
# Solución
## Solución 1: Ejecutar
Este reto nos enseña el comando chmod, el cual nos permite editar los permisos de un archivo en linux, en este caso, nuestra pista número 3 nos indica como realizarlo ejecutable con el comando:
```bash
chmod +x archivo
```
En este caso, el archivo vendría a ser una ruta (`./warm`), tras haberlo hecho un ejecutable, lo ejecutamos y nos regresa la línea:
```bash
./warm
Hello user! Pass me a -h to learn what I can do!
```
Al pasar el mismo archivo pero con la opción -h encontramos lo siguiente:
```
./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```

---
# Flag del reto
>picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}

---
# Notas adicionales

---
# Referencias

