# Nombre del reto
>Glory of the Garden

---
# Descripción
>This file contains more than it seems.
>Get the flag from [garden.jpg](https://challenge-files.picoctf.net/c_fickle_tempest/26ad1e959e2e6f15113d4dc2b43649625499d960e546d1b874357c6fcb8c5229/garden.jpg).

---
# Solución
Para este reto, deberemos de tener un editor hexadecimal (algo que nos permita ver la información sin procesar) de un archivo, para este caso usaremos el de kali linux:
```bash
wget https://challenge-files.picoctf.net/c_fickle_tempest/26ad1e959e2e6f15113d4dc2b43649625499d960e546d1b874357c6fcb8c5229/garden.jpg
hexeditor garden.jpg
```
Una vez que lo abrimos, podemos buscar una cadena con el comando `ctrl + w` o mover el archivo a formato de texto `ctrl + e`, de cualquier manera, la flag se encontrará cerca del final del archivo.

---
# Flag del reto
>picoCTF{more_than_m33ts_the_3y333f84d7c}

---
# Notas adicionales

---
# Referencias

[¿Qué #$!@ es un hex editor?](https://chatgpt.com/share/69ac97fd-5bcc-800b-beaf-f356968dfbab)