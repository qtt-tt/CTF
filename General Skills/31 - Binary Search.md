# Nombre del reto
>Binary Search

---
# Descripción
>Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
>
>Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!
>
>You can download the challenge files here:
- [challenge.zip](https://artifacts.picoctf.net/c_atlas/17/challenge.zip)
> `ssh -p 63788 ctf-player@atlas.picoctf.net`Using the password `f3b61b38`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

---
# Solución
Para este reto, se nos pide realizar una búsqueda binaria con un juego de adivinar el número que el sistema escoge aleatoriamente en el rango de 1 a 1000. Para esto, nos dan 10 intentos y ninguna pista más que iniciemos en 500. Para esto, podemos realizar el siguiente enfoque: **búsqueda binaria**

La búsqueda binaria se basa en que solo tenemos de dos opciones, arriba o abajo, verdadero o falso, 1 o 0. Para este reto se nos induce el concepto al jugar un juego de adivina mi número, para que la búsqueda binaria funcione aquí, debemos de iniciar en la mitad del rango de números, por lo que el flujo se podría ver de la siguiente manera:

| Número adivinado | Límite inferior | Límite superior |
| ---------------- | --------------- | --------------- |
| 500              | 1               | 1000            |
De esta forma, si pensamos que vamos a conseguir un número a través de iteraciones, solo nos queda pensar: ¿el número es más alto o es más bajo?

Con esta pregunta empieza la búsqueda binaria, ya que:
- Si es más alto, entonces toda la mitad de abajo (0 - 500) no será el número.
	- Nuestro rango cambia a 500 - 1000.
	- Ahora nuestro número adivinado es 750, pues es la mitad en el rango de números.
- Si es más bajo, entonces toda la mitad de arriba (500 - 1000) no será el número
	- Nuestro rango cambia a 0 - 500.
	- Ahora nuestro número adivinado es 250, pues es la mitad en el rango de números.
Esto se observa mejor en al siguiente tabla

| ¿Qué era? | Número adivinado | Límite inferior | Límite superior |
| --------- | ---------------- | --------------- | --------------- |
| Más alto  | 750              | 500             | 1000            |
| Más bajo  | 250              | 0               | 500             |
A partir de aquí, deberemos de hacernos la misma pregunta para cada una de las iteraciones, entonces, podemos pensarlo de la siguiente manera:
$$
numero~adivinado = \frac{Limite~superior~-~Limite~inferior}{2}
$$
Si nuestro número buscado es más alto:
$$
Limite~inferior=numero~adivinado
$$
$$
numero~adivinado = numero~adivinado+\frac{Limite~superior~-~Limite~inferior}{2}
$$
Si el número buscado es más bajo:
$$
Limite~superior=numero~adivinado
$$
$$
numero~adivinado = numero~adivinado+\frac{Limite~superior~-~Limite~inferior}{2}
$$
Por lo que solo nos falta seguir esta metodología hasta que encontremos el número que buscamos. Un script de Python que nos puede servir sería el siguiente:
```python
limite_inferior = 0
limite_superior = 1000
numero = int((limite_superior - limite_inferior)/2)
print(numero)
for x in range(10): # son 10 intentos
    opcion = input("higher (h), lower (l) o correcto (c)?: ")
    if (opcion == "c"):
        print("lo encontramos!")
        break
    elif (opcion == "h"):
        limite_inferior = numero
    elif (opcion == "l"):
        limite_superior = numero
    numero = limite_inferior + int((limite_superior - limite_inferior)/2)
    print(numero)
```

---
# Flag del reto
>picoCTF{g00d_gu355_6dcfb67c}

---
# Notas adicionales

---
# Referencias

