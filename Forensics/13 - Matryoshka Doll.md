# Nombre del reto
>Matryoshka Doll

---
# Descripción
>Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/0f5ef9c383aa83d319ccb01805f4b9499934bf6a44fdcb5a9f2039de92b6c24a/dolls.jpg)

---
# Solución
Descargar la imagen que se nos da y después acceder a los archivos dentro hasta conseguir la flag

Primero descargamos la imagen que se nos da, después para hacerlo más rápido, utilizamos el comando "binwalk -Me dolls.jpg" con ese comando hacemos que directamente vaya sacando todos los archivos dentro de la imagen, luego aplicamos un "find . -name "flag.txt" -exec cat {} +" para que busque entre las carpetas y nos de la flag

---
# Flag del reto
>picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}

---
# Notas adicionales

---
# Referencias

