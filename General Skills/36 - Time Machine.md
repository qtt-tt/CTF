# Nombre del reto
>Time Machine

---
# Descripción
>What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/68/challenge.zip)

---
# Solución
Para este reto, igual debemos de descargar y extraer el contenido de un zip, después de esto, debemos de revisar el log de los commits. Se hizo lo siguiente:
```bash
wget https://artifacts.picoctf.net/c_titan/68/challenge.zip
unzip challenge.zip
cd drop-in
git log
```
La "nota" que tiene el commit es la misma flag.

---
# Flag del reto
>picoCTF{t1m3m@ch1n3_b476ca06}

---
# Notas adicionales

---
# Referencias

