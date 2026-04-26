# Nombre del reto
>WebDecode

---
# Descripción
>Do you know how to use the web inspector?
>Start searching [here](http://titan.picoctf.net:59149/) to find the flag

---
# Solución
Tenemos 2 pistas: la primera, nos dice que debemos de navegar por la página; la segunda, que puede que la flag esté encriptada. Esto nos dice que deberemos de buscar cadenas raras.

Si navegas por las 3 páginas disponibles (home, about y contact) encontraremos que en la página de about hay un atributo raro:
```html
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMDdiOTFjNzl9">
```
Ahora, debemos de saber que notify_true suena raro, ¿no? además de la cadena gigante que hay que podemos pensar que es base64, entonces nos vamos a [cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQzWldKZmMzVmpZek56YzJaMWJHeDVYMlF6WXpCa1pXUmZNRGRpT1RGak56bDk) con esa cadenota, lo que nos da la flag.

---
# Flag del reto
>picoCTF{web_succ3ssfully_d3c0ded_07b91c79}

---
# Notas adicionales

---
# Referencias

[Cómo diferenciar base64](https://chatgpt.com/share/69abb463-3120-800b-8dc1-56a0fb9053e2).