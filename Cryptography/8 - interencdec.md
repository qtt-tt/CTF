# Nombre del reto
>interencdec

---
# Descripción
>Can you get the real meaning from this file.
>Download the file [here](https://artifacts.picoctf.net/c_titan/109/enc_flag).

---
# Solución
Al abrir el archivo encontraremos una cadena en base 64 (por los 2 = que están al final), al [decodificarla](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=WWlka00wSnhaR3R3UWxSWWRIRmhSM2cyWVVoc1ptRjZUbkZsVkd3eldWUk9jbGd5TUhkTmFrVjVUbnBWTkdaUlBUMG5DZz09) encontraremos otra cadena en base 64, la [decodificamos](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=ZDNCcWRrcEJUWHRxYUd4NmFIbGZhek5xZVRsM1lUTnJYMjB3TWpFeU56VTRmUT09) y encontramos el formato de la flag.
Aquí podemos intentar algunos métodos de desencriptación, pero lo más inteligente es meterlo a un identificador, nos dió caesar, por lo que encontramos nuestra flag.

---
# Flag del reto
>picoCTF{caesar_d3cr9pt3d_f0212758}

---
# Notas adicionales

---
# Referencias

