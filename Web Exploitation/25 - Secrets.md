# Nombre del reto
>Secrets

---
# Descripción
>We have several pages hidden. Can you find the one with the flag?
>The website is running [here](http://saturn.picoctf.net:52830/).

---
# Solución
Para este reto, deberemos de tener un ojo bastante audaz, pues aquí ver las carpetas será super importante, aunque lo voy a resumir:
1. Abrimos la página
2. Entramos al inspector y sources
3. Vemos una carpeta comprimida llamada secret
	1. Entramos a la carpeta secret como si fuera robots, o sea /secret/
4. Vemos otra carpeta llamada hidden
	1. Entramos otra vez a la carpeta, o sea /secret/hidden/
5. Vemos otra carpeta llamada superhidden
	1. Entramos otra vez a la carpeta, o sea /secret/hidden/superhidden/
6. Veremos de una el código de la página
	1. Encontramos la flag después del texto de "can you see me"

---
# Flag del reto
>picoCTF{succ3ss_@h3n1c@10n_51b260fe}

---
# Notas adicionales

---
# Referencias

