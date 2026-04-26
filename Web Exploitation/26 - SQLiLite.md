# Nombre del reto
>SQLiLite

---
# Descripción
>Can you login to this website?
>Try to login [here](http://saturn.picoctf.net:57104/).

---
# Solución
Para este reto, deberemos de usar nuevamente la inyección sql, pues al ingresar cualquier cosa como admin=123 y password=123 nos saltará una página donde nos dice la consulta que hace:
```sql
SELECT * FROM users WHERE name='123' AND password='123'
```
Sin hacerla larga (porque ya van 3 retos donde se usa xD) usaremos la cadena:
```sql
'or 1=1;
```
Pues esto nos dará que sea cierto y podremos entrar, pero la flag no se verá a simple vista, por lo que deberemos de ver el código fuente, y estará al lado

---
# Flag del reto
>picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}

---
# Notas adicionales

---
# Referencias

