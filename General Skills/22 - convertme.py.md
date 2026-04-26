# Nombre del reto
>convertme.py

---
# Descripción
>Run the Python script and convert the given number from decimal to binary to get the flag.
>[Download Python script](https://artifacts.picoctf.net/c/24/convertme.py)

---
# Solución
Para este reto, se nos solicita descargar y ejecutar un archivo de python, para esto, se usan las líneas de comandos:
```bash
wget https://artifacts.picoctf.net/c/24/convertme.py
python3 convertme.py
```
Este nos lanzará una pregunta: **If x is in decimal base, what is it in binary base?** (siendo que **x** es un número que puede variar en cada pregunta, en 3 intentos que se hizo después de encontrar la flag me dió: 87, 90 y 94), por lo que lo más recomendable es tener [un convertor a binario](https://toolbox.itsec.tamu.edu/#recipe=From_Decimal('Space',false)To_Binary('Space',8)) para solamente copiar el número decimal y tener correcta la respuesta, en este reto no importa si se mandan los 8 dígitos del binario.

---
# Flag del reto
>picoCTF{4ll_y0ur_b4535_722f6b39}

---
# Notas adicionales

---
# Referencias

