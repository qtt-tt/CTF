# Nombre del reto
>Cookies

---
# Descripción
>Who doesn't love cookies? Try to figure out the best one.
>[http://wily-courier.picoctf.net:59028/](http://wily-courier.picoctf.net:59028/)

---
# Solución
En este reto, se nos pide ingresar cookies hasta encontrar una cookie que nos de la bandera, al lanzar por ejemplo *snickerdoodle* nos da algo interesante, ya que nos lleva a otra página, pero si buscamos en el editor de galletas, vemos que tiene un valor numérico, si vamos ingresando poco a poco, podemos ver que cada valor tiene una galleta, por lo que podemos hacer lo siguiente en terminal:
```bash
curl http://wily-courier.picoctf.net:59028/check -H "Cookie: name=1" | grep "picoCTF"
```
el grep nos resaltará la flag.

---
# Flag del reto
>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}

---
# Notas adicionales

---
# Referencias

