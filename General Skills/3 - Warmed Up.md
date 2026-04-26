# Nombre del reto
>Warmed Up

---
# Descripción
>What is 0x3D (base 16) in decimal (base 10)?

---
# Solución
## Solución 1: Tabla ASCII
Una forma directa de dar con este reto es buscar su correspondencia en la [tabla ASCII](https://commons.wikimedia.org/wiki/File:ASCII-Table-wide.svg) recordemos que en esta tabla se encuentran 3 valores: decimal (azul), hexadecimal (rojo) y caracteres (verde). El reto nos solicita buscar el equivalente de 0x3d en el sistema decimal, por lo que al buscar encontramos que su valor decimal es 61.
## Solución 2: Conversión con Python
Recordemos que podemos transformar cualquier valor a decimal (pues es el sistema que Python maneja) al usar su conversión con *int(número, base)*, este método se puede encontrar de la siguiente manera:
```python
# Recibimos el número hexadecimal
hex = "0x3d"
print("El valor del hexadecimal es:", hex)

# Le decimos a python que lo interprete como decimal (diciendole que está en base 16)
decimal = int(hex, 16)
print("El valor decimal es:", decimal)
```
## Solución 3: Cyberchef
A este momento, podemos saber que al usar la página Cyberchef podemos resolver retos de criptografía si sabemos a que nos enfrentamos, de modo que la solución es tan sencilla como indicarle desde que base (from hex en este caso) hacia que base (to decimal) lo vamos a convertir.
[Solución con cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Hex('Auto')To_Decimal('Space',false)&input=MHgzRA)

---
# Flag del reto
>picoCTF{61}

---
# Notas adicionales

---
# Referencias

