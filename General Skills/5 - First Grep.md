# Nombre del reto
>First Grep

---
# Descripción
>Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.
>
>The flag is in this [file (Este link lo descarga)](https://challenge-files.picoctf.net/c_fickle_tempest/92807684f3e52665caaf90d69e1e661f990b8731b2f8005e18631be23ff991bb/file).

---
# Solución
## Solución 1: comando grep en Linux
Se usó el comando grep en la línea de comandos de Linux, para esto recordemos que la sintaxis de grep es: **grep *patrónTexto* *archivo*** entonces, se descargó el archivo usando el comando **wget *url*** para conseguir el archivo en la terminal embebida de picoCTF. Una vez hecho esto se usó el comando grep para obtener nuestra información y encontramos resaltado en rojo nuestra flag. Mi proceso fue el siguiente:
```bash
wget https://challenge-files.picoctf.net/c_fickle_tempest/92807684f3e52665caaf90d69e1e661f990b8731b2f8005e18631be23ff991bb/file
grep picoCTF file
```

---
# Flag del reto
>picoCTF{grep_is_good_to_find_things_eb80073D}

---
# Notas adicionales
Un grep es básicamente una forma de buscar patrones de texto en un archivo.

---
# Referencias

