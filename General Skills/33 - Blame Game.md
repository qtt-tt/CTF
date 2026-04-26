# Nombre del reto
>Blame Game

---
# Descripción
>Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/72/challenge.zip)

---
# Solución
Para este reto, nos proporcionan un zip con un archivo de python y un conjunto de commits gigantes, esto hace que nuestro trabajo sea buscar quien tuvo la culpa (de aquí el nombre), entonces lo que se ejecuta son los siguientes comandos:
```bash
wget https://artifacts.picoctf.net/c_titan/72/challenge.zip
unzip challenge.zip
cd drop-in
git blame message.py
```
Este último comando, nos lleva a una pantalla que nos dice: el id del commit, el autor, la fecha y hora y el contenido modificado.

En este caso, el usuario es nuestra bandera.

---
# Flag del reto
>picoCTF{@sk_th3_1nt3rn_b64c4705}

---
# Notas adicionales

---
# Referencias

