# Nombre del reto
>extensions

---
# Descripción
>This is a really weird text file. Can you find the flag?
>Get the flag from [TXT](https://challenge-files.picoctf.net/c_fickle_tempest/31fe772e6a4c71e867af0b2a93818e06d8f8ebf8af2a9615495d00356ff576da/flag.txt).

---
# Solución
Para esto, debemos de saber el concepto de los magic bytes (que básicamente son una firma de los tipos de archivos), en este caso, primero que nada debemos de ver qué tipo de archivo es flag.txt (archivo descargado).
```bash
file flag.txt
```
Esto nos dirá que es una imagen png, entonces nos toca cambiar la extensión para que podamos abrirlo, ¿pero como se supo que era una imagen?

Fácil, al correr la línea `xxd flag.txt | head` encontraremos la firma del archivo, en este caso fue: `8950 4e47 0d0a 1a0a` lo cual corresponde a la firma de los archivos png.

Al cambiar la extensión y abrir la imagen, encontraremos nuestra bandera.
```bash
mv flag.txt flag.png
open flag.png
```

---
# Flag del reto
>picoCTF{now_you_know_about_extensions}

---
# Notas adicionales

---
# Referencias
[¿Qué $#&@ son los magic bytes?](https://chatgpt.com/share/69ac9aea-f2d8-800b-9094-6ec55f7872fd)
