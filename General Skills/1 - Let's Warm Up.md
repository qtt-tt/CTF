# Nombre del reto
>Lets Warm Up

---
# Descripción
>If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

---
# Solución
## Solución 1 Cyberchef
Se ingresa el hexadecimal **0x70** en cyber chef, se selecciona la receta **from hex** ya que vamos transformar de hexadecimal, esto nos resuta en la letra *p*
[Solución con cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Hex('Auto')&input=MHg3MA)
## Solución 2 Conversión con Python
Se realiza la transformación de hexadecimal a decimal, entonces se busca el carácter del número decimal (que representa su valor en la tabla ascii).
```python
# Inicializamos valor hexadecimal
hex_num = "0x70"
print("Valor hexadecimal dado: ", hex_num)

# Se mueve a decimal (base 10)
decimal = int(hex_num, 16)
print("Valor decimal del hexadecimal: ", decimal)

# Búsqueda del caracter
letra = chr(decimal)
print("Letra que corresponde a ese valor decimal:", letra)
```
## Solución 3 Conversión manual
Para este método podemos buscar una conversión manual al pensar en como funcionan los valores hexadecimales. Primero que todo, se dividen en dos valores, al momento de obtener algún valor hexadecimal obtenemos una cadena como *0x70*, pero lo que nos va a interesar son los últimos dos dígitos, ya que la parte de **0x** se usa solamente para indicar que es un valor hexadecimal.
Un hexadecimal se compone de dos números que representan un valor del 0 al 9 y del A al F, correspondiendo estos valores al número máximo de bits que puede tener. Siendo que un byte se divide en dos y se toma el valor en base a cuales están prendidos. Por ejemplo:

| Número binario | Primeros 4 bits | Últimos 4 bits | Valor primeros | Valor últimos | Hexadecimal |
| -------------- | --------------- | -------------- | -------------- | ------------- | ----------- |
| 01100011       | 0110            | 0011           | 6              | 3             | 0x63        |

Entonces, para este reto, podemos hacer el proceso inverso de la siguiente manera:

| Hexadecimal | Valor primeros | Valor últimos | Primeros 4 bits | Últimos 4 bits | Número binario |
| ----------- | -------------- | ------------- | --------------- | -------------- | -------------- |
| 0x70        | 7              | 0             | 0111            | 0000           | 01110000       |

De esta forma, solamente necesitamos obtener el valor del número binario el cual es ***112*** entonces este valor solamente se busca en una tabla de conversión de [Números ASCII](https://commons.wikimedia.org/wiki/File:ASCII-Table-wide.svg) y nos resulta que es representado por la p.
## Solución 4. Conversión con tabla ASCII directa
Recordando que las computadoras guardan los caracteres en números y no directos, podemos encontrar alguna tabla de [Valores ASCII](https://commons.wikimedia.org/wiki/File:ASCII-Table-wide.svg).
Ya que la tenemos, solamente nos queda buscar el valor hexadecimal (marcado en rojo) que corresponda, para esto debemos recordar que solo se toman los últimos dos dígitos, pues el 0x indica que es un valor hexadecimal.
Según la tabla nos indica que 70 corresponde a la letra p.

---
# Flag del reto
>picoCTF{p}

---
# Notas adicionales

Hay otras formas de resolver esto, se puede indagar en más formas de resolverlo.

---
# Referencias

