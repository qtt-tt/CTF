# Nombre del reto
>Java Code Analysis!

---
# Descripción
>BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book! Here are the credentials to get you started:
>Username: "user"
>Password: "user"
>Source code can be downloaded [here](https://artifacts.picoctf.net/c/480/bookshelf-pico.zip). Website can be accessed [here!](http://saturn.picoctf.net:57198/).

---
# Solución
Primero es entrar a la página y conseguir allí el JWT que es para el usuario normal, después revisarlo con el decoder, luego de eso entramos al código y obtenemos el usuario, la contraseña de admin, además de la llave secreta que solamente es "1234", todo eso lo pasamos al encoder y conseguimos la nueva JWT de admin, después en la página editamos el almacenamiento local con el nuevo JWT y obtenemos la flag

---
# Flag del reto
>picoCTF{w34k_jwt_n0t_g00d_602ce414}

---
# Notas adicionales

---
# Referencias

