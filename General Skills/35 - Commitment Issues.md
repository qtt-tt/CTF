# Nombre del reto
>Commitment Issues

---
# Descripción
>I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)

---
# Solución
Para este reto, igual deberemos de descargar un zip que contiene un conjunto de cambios de git y un archivo, en este, deberemos de buscar los commits en el log de git (librito de cambios) y acceder a un commit en específico. Se hizo lo siguiente:
```bash
wget https://artifacts.picoctf.net/c_titan/138/challenge.zip
unzip challenge.zip
cd drop-in
git log
git checkout b562f0b425907789d11d2fe2793e67592dc6be93
nano message.txt
```
En mi caso, b562f0b425907789d11d2fe2793e67592dc6be93 era el commit al que sele atribuía el mensaje: Create flag, de modo que sabía que debía entrar a ese.

---
# Flag del reto
>picoCTF{s@n1t1z3_c785c319}

---
# Notas adicionales

---
# Referencias

