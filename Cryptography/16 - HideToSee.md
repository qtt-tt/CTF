# Nombre del reto
>HideToSee

---
# Descripción
>How about some hide and seek heh?
>Look at this image [here](https://artifacts.picoctf.net/c/237/atbash.jpg). 

---
# Solución
Aplicamos los siguientes comandos en kali:
```bash
sudo apt install steghide
steghide --extract -sf atbash.jpg
cat encrypted.txt
```
Y lo decodificamos.

---
# Flag del reto
>picoCTF{atbash_crack_05b2a65a}

---
# Notas adicionales

---
# Referencias

