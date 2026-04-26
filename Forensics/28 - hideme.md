# Nombre del reto
>hideme

---
# Descripción
>Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/259/flag.png).

---
# Solución
Primero descargamos la imagen, después usamos binwalk, con eso podemos ver que tiene archivos dentro de la imagen, por lo que usamos "binwalk -e" y con ello podemos obtener la imagen que contiene la flag

---
# Flag del reto
>picoCTF{Hiddinng_An_imag3_within_@n_ima9e_85e04ab8}

---
# Notas adicionales

---
# Referencias

