# Nombre del reto
>so meta

---
# Descripción
>Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/fea53d4b5a95f9e78fc25c77dd5332d9ef4aa71d2e64ea96bbe171e0300741b2/pico_img.png).

---
# Solución
Para este reto, deberemos de adentrarnos en los meta datos de un archivo, para esto se usó la herramienta exiftool, para la cual, su uso fue el siguiente:
```bash
wget https://challenge-files.picoctf.net/c_fickle_tempest/fea53d4b5a95f9e78fc25c77dd5332d9ef4aa71d2e64ea96bbe171e0300741b2/pico_img.png
exiftool pico_img.png
```
Esto nos dará nuestra flag en la parte del autor!

---
# Flag del reto
>picoCTF{s0_m3ta_bc056477}

---
# Notas adicionales

---
# Referencias

[¿Qué $#&@ son los meta datos?](https://chatgpt.com/share/69ac9f74-0400-800b-a8d0-c1072561b177).