# Nombre del reto
>JaWT Scratchpad

---
# Descripción
>Check the admin scratchpad!
>[http://fickle-tempest.picoctf.net:60827](http://fickle-tempest.picoctf.net:60827)

---
# Solución
Para empezar, nuestra pista nos sugiere el uso de las cookies, por lo que se volverá a usar la extensión que se usó en el reto 8 - Cookies, entonces, si buscamos en las cookies tras habernos "registrado" en la página, encontramos una cookie llamada jwt, la cual si la buscamos en un [decodificador o codificador JWT](https://www.jwt.io/) nos mostrará que esa cadena gigante es nuestro usuario, por lo que, ahora, podemos intentar codificar un JWT con el nombre de admin, pero nos falta una contraseña para codificar correctamente nuestra llave. Para esto, usaremos la biblioteca **john**, enfocada en crackear contraseñas. Se usa el archivo rockyou.txt (alojado en `/usr/share/wordlists`, cabe avisar que se debe de descomprimir con `gzip -d /usr/share/wordlists/rockyou.txt.gz`), ahora, se aplica el siguiente comando:
```bash
john -w=/usr/share/wordlists/rockyou.txt
```
Esto nos resultará en una contraseña: *ilovepico* la cual si la introducimos en el codificador JWT, ahora si nos dará el valor de la cookie para ingresar como admin y nos muestre la flag

---
# Flag del reto
>picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}

---
# Notas adicionales
Se usó kali Linux para resolverlo

---
# Referencias

[JSON Web Tokens](https://chatgpt.com/share/69a381e6-ab70-800b-b83a-cade97e07783).