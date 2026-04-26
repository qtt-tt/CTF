# Nombre del reto
>Irish-Name-Repo 1

---
# Descripción
>Do you think you can log us in? Try to see if you can login!
>[http://fickle-tempest.picoctf.net:54642](http://fickle-tempest.picoctf.net:54642).

---
# Solución
Al entrar a la página, encontramos que básicamente es un listado de personas irlandesas, pero el reto nos pide entrar en el log in. Para esto, nos dan dos pistas, ambas relacionadas con bases de datos, en la primera nos preguntan si los usuarios se guardan en una base de datos, en la segunda, como el sitio verifica nuestra identidad, esto se hace con consultas SQL, por ejemplo:
```sql
SELECT * FROM users WHERE name='irish' AND password='contrasena'
```
En esta sentencia, nuestra página busca los usuarios que tengan cierto nombre y cierta contraseña y pues esto es la validación, mientras regrese un usuario, pues puede pasar (es verdadera la sentencia).

Ahora, en este caso, tenemos que pensar en como lograr que esta verificación no suceda, y tenemos que pensar en una sentencia que nos diga: siempre es verdadero. Un ejemplo muy sencillo: `1=1`, pero ahora, como lo podemos meter ahí? Pues simple y sencillamente agregándolo como una opción alterna en el campo de las contraseñas, para que quede algo así nuestro log in:
```
usuario: irish
contraseña: 'or 1=1;
```
Y esto nos regresa la bandera

---
# Flag del reto
>picoCTF{s0m3_SQL_85832275}

---
# Notas adicionales
>Para saber que usuario es del admin, debemos de inspeccionar el log in, y establecer el modo debug en 1, para que nos muestre los usuarios que existen.

---
# Referencias

[Inyección SQL](https://chatgpt.com/share/69a3687f-255c-800b-a6ab-e17bd5d64726).