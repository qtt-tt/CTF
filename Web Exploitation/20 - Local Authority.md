# Nombre del reto
>Local Authority

---
# Descripción
>Can you get the flag?
>Go to this [website](http://saturn.picoctf.net:55108/) and see what you can discover.

---
# Solución
Al entrar, encontramos un login que no tiene nada de raro, solo nos dice que debemos de introducir solamente letras y números, al entrar nos dirá que el login fue fallido, la pista nos pregunta el como verificará la contraseña el sitio, podemos inspeccionar el sitio con el fin de buscar una vulnerabilidad, la cual la encontraremos en el apartado de sources.

Cuando nos regresa la contraseña encontraremos un archivo (que no está antes) en el repertorio, el cual es secure.js con el siguiente código:
```js
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
Ya que tenemos esto solo nos queda copiar y pegar el usuario y la contraseña.

---
# Flag del reto
>picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}

---
# Notas adicionales

---
# Referencias

