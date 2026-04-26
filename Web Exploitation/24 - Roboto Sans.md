# Nombre del reto
>Roboto Sans

---
# Descripción
>The flag is somewhere on this web application not necessarily on the website. Find it.
>Check [this](http://saturn.picoctf.net:63745/) out.

---
# Solución
El reto nos sugiere ir a robots.txt, el cual nos da lo siguiente:
```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```
Podemos ver que hay texto en base 64 (por los 2 =), entonces podemos ir a desencriptarlo en [cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YW5NdmJYbG1hV3hsTG5SNGRBPT0), esto nos dará una dirección: js/myfile.txt, al entrar nos dará nuestra flag.

---
# Flag del reto
>picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}

---
# Notas adicionales

---
# Referencias

