# Nombre del reto
>What Lies Within

---
# Descripción
>There's something in the [building](https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png). Can you retrieve the flag?

---
# Solución
Para conseguir la flag, la pista nos da un camino a seguir, diciendo que habrá un mensaje encriptado en alguna parte, entonces, debemos de ponernos a pensar:
- No es un texto, por lo que no hay mensajes encriptados a simple vista.
- No hay nada raro en la parte de texto de nuestra imagen png.
- No hay datos raros en los magic bytes.
- No hay datos raros en los metadatos de nuestra imagen.
Por lo que solo puede ser un mensaje encriptado "invisible", por lo que veremos si se aplicó esteganografía en un [decodificador](https://stylesuxx.github.io/steganography/). Al cargar la imagen encontraremos nuestra flag.

---
# Flag del reto
>picoCTF{h1d1ng_1n_th3_b1t5}

---
# Notas adicionales

---
# Referencias

[¿Qué $#&@ es la esteganografía?](https://chatgpt.com/share/69acbe63-8140-800b-a0ba-6c3903b80dd6).