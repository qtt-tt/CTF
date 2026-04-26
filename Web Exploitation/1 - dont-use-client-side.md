# Nombre del reto
>dont-use-client-side

---
# Descripción
>Can you break into this super secure portal?
>[http://fickle-tempest.picoctf.net:65138](http://fickle-tempest.picoctf.net:65138)

---
# Solución
Al entrar a la página web, encontramos solamente un fondo azul con una caja donde podemos introducir una contraseña, al ingresar cualquier palabra (menos la bandera) nos dará un error donde nos dice que la contraseña está incorrecta, al abrir el código fuente de la página, encontramos lo siguiente:
```html
<html>
<head>
<title>Secure Login Portal</title>
</head>
<body bgcolor=blue>
<!-- standard MD5 implementation -->
<script type="text/javascript" src="md5.js"></script>

<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == 'eb02') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_2') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'b45}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>
<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:yellow">
<div style="text-align:center">
<p>This is the secure login portal</p>
<p>Enter valid credentials to proceed</p>
<form action="index.html" method="post">
<input type="password" id="pass" size="8" />
<br/>
<input type="submit" value="verify" onclick="verify(); return false;" />
</form>
</div>
</div>
</body>
</html>
```
Ahora, ¿Qué es lo que debemos de revisar aquí? pues, encontramos una parte interesante en el input de la contraseña, ya que al hacer click (onclick) se manda a llamar a la función verify(), la cual tiene la siguiente estructura:
```javascript
function verify() {
checkpass = document.getElementById("pass").value;
split = 4;
if (checkpass.substring(0, split) == 'pico') {
  if (checkpass.substring(split*6, split*7) == 'eb02') {
	if (checkpass.substring(split, split*2) == 'CTF{') {
	 if (checkpass.substring(split*4, split*5) == 'ts_p') {
	  if (checkpass.substring(split*3, split*4) == 'lien') {
		if (checkpass.substring(split*5, split*6) == 'lz_2') {
		  if (checkpass.substring(split*2, split*3) == 'no_c') {
			if (checkpass.substring(split*7, split*8) == 'b45}') {
			  alert("Password Verified")
			  }
			}
		  }
  
		}
	  }
	}
  }
}
else {
  alert("Incorrect password");
}

}
```
En la cual podemos ver que se realiza una división constante de la cadena de la contraseña, por lo que, viendo que `splits = 4` podemos darnos una idea de como lo realiza:
- La función substring(x,y) divide la cadena de la cadena en secciones, la sección que compara va desde x hasta y.
- x podemos ver que toma valores múltiplos de split (recordando que split es 4)
- y podemos ver que toma también valores de split (recordando que split es 4)
Lo que tenemos que hacer aquí, es ordenar siguiendo la secuencia de lo splits, aunque podemos armarla según el valor de multiplicación que tiene splits. O lo que sería, encontrar la siguiente tabla:

| valor X | valor Y | cadena |
| ------- | ------- | ------ |
| 0       | split   | pico   |
| split   | split*2 | CTF{   |
| split*2 | split*3 | no_c   |
| split*3 | split*4 | lien   |
| split*4 | split*5 | ts_p   |
| split*5 | split*6 | lz_2   |
| split*6 | split*7 | eb02   |
| split*7 | split*8 | b45    |
Ahora, solo para verificar, podemos ingresarla en el recuadro, lo que nos deberá decir que está verificada.

---
# Flag del reto
>picoCTF{no_clients_plz_2eb02b45}

---
# Notas adicionales

---
# Referencias

