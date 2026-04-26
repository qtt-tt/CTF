# Nombre del reto
>Dont-You-Love-Banners

---
# Descripción
>Can you abuse the banner? The server has been leaking some crucial information on `tethys.picoctf.net 63002`. Use the leaked information to get to the server. To connect to the running application use `nc tethys.picoctf.net 54663`. From the above information abuse the machine and find the flag in the /root directory.

---
# Solución
Primero, entramos a la primera página, esta nos dará una linea rara como: `SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234`. Copiaremos la última parte (`My_Passw@rd_@1234`) y nos conectaremos a la segunda página. Contestaremos las 3 preguntas (lo que copiamos, def con, John Draper) y nos dejará entrar, como nos pide entrar a /root, pues entramos y encontramos la flag pero no podemos verla, de aquí haremos dos cosas:
```bash
mv banner banner_backup  
ln -s /root/flag.txt banner
```
Ahora, nos desconectamos de la página, y cuando entramos pues nos dará la flag

Primero es entrar a la pagina de apoyo que tiene la contraseña y llevárnosla, luego a la página del reto y allí contestamos las 3 preguntas que nos hace, después borramos el banner "rm banner" y luego hacemos un link simbólico "ls -s /root/flag.txt /home/player/banner" entre la flag y el banner para que la próxima vez que nos conectemos directamente nos abra la flag y con ello al volver a conectarnos, tenemos la flag

---
# Flag del reto
>picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_8126c9b0}

---
# Notas adicionales

---
# Referencias

