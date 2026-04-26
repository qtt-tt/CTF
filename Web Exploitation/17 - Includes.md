# Nombre del reto
>Includes

---
# Descripción
>Can you get the flag?
>Go to this [website](http://saturn.picoctf.net:62540/) and see what you can discover.

---
# Solución
El reto nos pide entrar a una página web, donde nos habla de directorios en la página web, o sea, otros archivos que se encuentran en la misma carpeta u otras donde está el html que estamos viendo, en este caso, debemos de inspeccionar la página web.

Al entrar en la pestaña sources encontramos 3 archivos: (index), script.js y style.css. Al buscar en (index) encontramos una parte interesante, pues se hace una llamada a una función llamada greetings, la cual nos devuelve un mensaje: `This code is in a separate file!`, entonces debemos de buscar, el primer archivo externo que podemos buscar es el .js, pues existe una funcionalidad. Esto nos dará una parte de la llave; si nos vamos al .css encontraremos la primera parte.

---
# Flag del reto
>picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}

---
# Notas adicionales

---
# Referencias

