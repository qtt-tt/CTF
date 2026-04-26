# Nombre del reto
>c0rrupt

---
# Descripción
>We found this [file](https://challenge-files.picoctf.net/c_fickle_tempest/87bdc8ce30b177d033b3d68bca4647950bb07304032861baa912ebe08701d355/mystery). Recover the flag.

---
# Solución
Para esto, deberemos de tener una herramienta instalada llamada pngcheck:
```bash
sudo apt install pngcheck
```
Con esta, ya podremos revisar la integridad de nuestros archivos png, ahora, para nuestro caso nos iremos directamente a corregir los valores de nuestro archivo. Debemos de establecer correctamente los nombres de cada chunk con el fin que se vaya la corrupción de nuestro archivo png.

**00000000** 89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52

**00000010** 00 00 06 6A  00 00 04 47   08 02 00 00  00 7C 8B AB

**00000020**  78 00 00 00  01 73 52 47   42 00 AE CE  1C E9 00 00

**00000030**  00 04 67 41  4D 41 00 00   B1 8F 0B FC  61 05 00 00

**00000020**  00 09 70 48  59 73 00 00   16 25 00 00  16 25 01 49

**00000050**  52 24 F0 00  00 FF A5 49   44 41 54 78  5E EC BD 3F

Después de esto, podemos abrirla y ver que todo esté bien
``` bash
pngcheck -v mystery
open mystery
```

---
# Flag del reto
>picoCTF{c0rrupt10n_1847995}

---
# Notas adicionales

---
# Referencias

[¿Qué $#&@ son los chunks?](https://chatgpt.com/share/69b0f9a7-7528-800b-a03f-096a957536a6).