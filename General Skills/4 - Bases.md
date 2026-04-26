# Nombre del reto
>Bases

---
# Descripción
>What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

---
# Solución
## Solución 1: Cyberchef
Para saber a que nos enfrentamos debemos de empezar a notar algunas cosas que tiene que ver con bases, por ejemplo en esta nos encontramos lo siguiente:
- Usa mayúsculas y minúsculas.
- Tiene números del 0 al 9.
- Su longitud es múltiplo de 4 (la longitud de esta cadena es de 20).
Estas son características de base64 (además de la regla común de: *Si parece texto raro, tiene mayúsculas y minúsculas, y no tiene símbolos raros, muy probablemente sea base64*)
Por lo que se introduce en Cyberchef para intentar su decodificación, lo cual, nos dio un texto al darle la receta *From base64*
[Solución con cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE)
## Solución 2: base64 con Python
Python nos ofrece una biblioteca centrada en el uso de la base64, por lo que a continuación, se encuentra el código que se puede usar:
```python
import base64

cadena = "bDNhcm5fdGgzX3IwcDM1"
cadenaDecodificada = base64.b64decode(cadena) # Decodificamos la base 64
cadenaDecodificada = cadenaDecodificada.decode("utf-8") # Movemos los bytes a texto legible
print("Cadena encontrada:", cadenaDecodificada)
```

---
# Flag del reto
>picoCTF{l3arn_th3_r0p35}

---
# Notas adicionales

---
# Referencias

