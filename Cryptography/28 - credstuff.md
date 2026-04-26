# Nombre del reto
>credstuff

---
# Descripción
>We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

---
# Solución
Descomprimimos el archivo, buscamos la línea del usuario y encontramos que es la 378, buscamos esa misma en la de contraseñas y encontramos una flag cifrada, usamos un [identificador](https://www.dcode.fr/cipher-identifier) y encontramos que debe de ser un cifrado ROT, por lo que [intentamos](https://www.dcode.fr/rot-cipher) y encontramos la flag.

---
# Flag del reto
>picoCTF{C7r1F_54V35_71M3}

---
# Notas adicionales

---
# Referencias

