# Nombre del reto
>2Warm

---
# Descripción
>Can you convert the number 42 (base 10) to binary (base 2)?

---
# Solución
## Solución 1: Python con bin()
Como nos dan el número **42** en *base 10*, lo único que nos queda es moverlo a base 2, como Python maneja los números en base 10, la función bin() nos ayuda a salir de esta base. El código usado fue el siguiente:
```python
# Inicializamos variable
numero = 42

# Convertimos a binario (base 2)
binario = bin(numero)
print(binario)
```
## Solución 2: Usando divisiones manuales
Para movernos entre bases, una de las formas que se puede hacer es hacer una división entera, guardando el resultado y el residuo, de forma que se va dividiendo (en este caso) entre 2 para obtener el resultado de nuestro binario. 
Las divisiones tomarían una estructura bastante sencilla y repetitiva, la podemos pensar de la siguiente manera:

| ***Iteración*** | *División hecha* | *Resultado* | *Residuo* |
| --------------- | :--------------: | :---------: | :-------: |
| **1**           |      $42/2$      |     21      |     0     |
| **2**           |      $21/2$      |     10      |     1     |
| **3**           |      $10/2$      |      5      |     0     |
| **4**           |      $5/2$       |      2      |     1     |
| **5**           |      $2/2$       |      1      |     0     |
| **6**           |      $1/2$       |      0      |     1     |

## Solución 3: Usando divisiones con Python
Las divisiones se pueden "automatizar" con Python usando el siguiente código:
```python
# Inicializamos variable
numero = 42
print("Número en base10 dado: ", numero)

binario = ""
while (numero > 0):
    binario = str(numero % 2) + binario # Operación módulo, regresa el residuo
    numero = numero // 2 # Dice cuantas veces cabe el 2 en el número
print("Valor del número en base 2(binario):", binario)
```
## Solución 4: Cyberchef
Cyberchef también nos ayuda a la hora de mover de bases, para esto escogemos desde que base se va a mover (*from decimal* en este caso, ya que vamos a mover de base10 o decimal) y hacia cual base se va a mover (*to binary* en este caso, ya que vamos a mover a base2 o binario). Aunque en esta ves, nos da la cadena 00101010, pero para picoCTF no nos admite esa flag entera, solo debemos de introducir desde el bit prendido (101010).
[Solución con cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Decimal('Space',false)To_Binary('Space',8)&input=NDI)

---
# Flag del reto
>picoCTF{101010}

---
# Notas adicionales

---
# Referencias

