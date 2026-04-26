# Nombre del reto
>Collaborative Deployment

---
# Descripción
>My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_titan/70/challenge.zip)

---
# Solución
Para este reto, tendremos que meternos a corregir errores del merge de varias ramas de un archivo de git, para empezar, descargaremos y descomprimiremos el archivo, de ahí, definiremos nuestro usuario y empezaremos con el manejo del conflicto de merging. El proceso es el siguiente:
```bash
wget https://artifacts.picoctf.net/c_titan/70/challenge.zip
unzip challenge.zip
cd drop-in
git config --global user.email "elCorreo"
git config --global user.email "elNombre"
git merge feature/part-1
git merge feature/part-2
nano flag.py
git commit -a
git merge feature/part-3
nano flag.py
git commit -a
python3 flag.py
```
En cada `nano flag.py` se corrige el archivo, esto se logra borrando el `>>>>> HEAD`, `=====` y `<<<<<< branch`

---
# Flag del reto
>picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_7ffa0077}

---
# Notas adicionales

---
# Referencias

