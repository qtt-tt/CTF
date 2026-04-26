# Nombre del reto
>Get aHead

---
# Descripción
>Find the flag being held on this server to get ahead of the competition
>[http://wily-courier.picoctf.net:54353/](http://wily-courier.picoctf.net:54353/)

---
# Solución
Podemos usar curl para solicitar datos de una página web, en este caso el título nos da una pista: head, investigando, encontramos que head es una forma de recibir los encabezados de una página web.
```bash
curl -I http://wily-courier.picoctf.net:54353/
```
Esto nos regresará los valores de cada encabezado, como lo son:
```
HTTP/1.1 200 OK
Date: Thu, 26 Feb 2026 00:24:11 GMT
Server: Apache/2.4.38 (Debian)
X-Powered-By: PHP/7.2.34
flag: picoCTF{r3j3ct_th3_du4l1ty_8b13f07}
Content-Type: text/html; charset=UTF-8
```
Y aquí, encontramos la flag.

---
# Flag del reto
>picoCTF{r3j3ct_th3_du4l1ty_8b13f07}

---
# Notas adicionales

---
# Referencias

[Métodos HTTP](https://chatgpt.com/share/699f9784-f688-800b-a517-55bb54e1f56f).