# Nombre del reto
>binhexa

---
# Descripción
>How well can you perfom basic binary operations?
>
>Start searching for the flag here `nc titan.picoctf.net 59491`

---
# Solución
Para este reto nos solicitan saber un poco sobre las operaciones de bits, para esto, debemos de saber lo siguiente:

| Operación      | A nivel de | Símbolo usado | Significado                          | Cómo hacerla                                                                                                     |
| -------------- | ---------- | ------------- | ------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Suma           | Números    | +             | Sumar ambos en decimal.              | Convertir ambos en decimal, luego sumar.                                                                         |
| Multiplicación | Números    | *             | Multiplicar ambos en decimal.        | Convertir ambos en decimal, luego multiplicar.                                                                   |
| OR             | Bits       | \|            | Comparar dos bits prendidos.         | Comparar bit por bit (pos 1 con pos 1, pos 2 con pos 2...), si alguno de los dos bits es 1, el resultado será 1. |
| AND            | Bits       | &             | Comparar dos bits prendidos.         | Comparar bit por bit (pos 1 con pos 1, pos 2 con pos 2...), si alguno de los dos bits es 0, el resultado será 0. |
| Right Shift    | Bits       | >>            | Mover todos los bits a la derecha.   | Se recorren los bits a la derecha, colocando 0                                                                   |
| Left Shift     | Bits       | <<            | Mover todos los bits a la izquierda. | Se recorren los bits a la izquierda, colocando 0                                                                 |
Ahora, en el reto, nos proporcionarán dos números en binario, y nos pedirán realizarles ciertas operaciones. Aquí un ejemplo de los números que nos pidieron.

| Número 1 (binario) | Número 1 (decimal) | Número 2 (binario) | Número 2 (decimal) |
| ------------------ | ------------------ | ------------------ | ------------------ |
| 01000101           | 69                 | 11110011           | 243                |
Además, para este reto tendremos que tener: un conversor [binario-decimal](https://toolbox.itsec.tamu.edu/#recipe=From_Base(2)), un conversor [decimal-binario](https://toolbox.itsec.tamu.edu/#recipe=To_Base(2)), un conversor a [hexadecimal](https://toolbox.itsec.tamu.edu/#recipe=From_Base(2)To_Base(16)). Ya que tenemos esta información, podemos realizar las operaciones a libertad, empecemos poco a poco.
- **Suma ($+$)**: Lo que se hará será sumar la representación de decimal de cada número, su resultado se representará en binario.
En el ejemplo que viene adjunto, se realiza:
$$
69~+~243=312
$$
Una vez que lo tenemos hecho, se transforma a [binario](https://toolbox.itsec.tamu.edu/#recipe=To_Base(2)&input=MzEy).
- **Multiplicación ($*$)**: Lo que se hará será multiplicar la representación de decimal de cada número, su resultado se representará en binario.
En el ejemplo que viene adjunto, se realiza:
$$
69~\cdot{}~243=16767
$$
Una vez que lo tenemos hecho, se transforma a [binario](https://toolbox.itsec.tamu.edu/#recipe=To_Base(2)&input=MTY3Njc).
- **Or ($|$)**: Lo que hará será comparar cada bit, buscando que cada uno represente la operación OR que se hace con True o False.
En el ejemplo que viene adjunto, se compara de la siguiente manera:

| Números   | Bit 1 | Bit 2 | Bit 3 | Bit 4 | Bit 5 | Bit 6 | Bit 7 | Bit 8 |
| --------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| Número 1  | 0     | 1     | 0     | 0     | 0     | 1     | 0     | 1     |
| Número 2  | 1     | 1     | 1     | 1     | 0     | 0     | 1     | 1     |
| Resultado | 1     | 1     | 1     | 1     | 0     | 1     | 1     | 1     |
El resultado (11110111) se inserta directo en la terminal así en binario.
- **And ($&$)**: Lo que se hará será comparar cada bit, buscando que cada uno represente la operación AND que se hace con True o False.
En el ejemplo que viene adjunto, se compara de la siguiente manera:

| Números   | Bit 1 | Bit 2 | Bit 3 | Bit 4 | Bit 5 | Bit 6 | Bit 7 | Bit 8 |
| --------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| Número 1  | 0     | 1     | 0     | 0     | 0     | 1     | 0     | 1     |
| Número 2  | 1     | 1     | 1     | 1     | 0     | 0     | 1     | 1     |
| Resultado | 0     | 1     | 0     | 0     | 0     | 0     | 0     | 1     |
El resultado (01000001) se inserta directo en la terminal así en binario.
- **Right Shift($>>$)**: Lo que se hará será recorrer cada bit a la derecha n pasos, generalmente se indica algo así: >>1, >>2, de forma que se sabe cuantos bits se recorrerán, aunque en este reto se dice al momento de hacer la pregunta.
Esta operación, solo se realiza en un número, en el reto se nos pide realizar esto con un solo salto, entonces se vería algo así:

| Números     | Bit 1 | Bit 2 | Bit 3 | Bit 4 | Bit 5 | Bit 6 | Bit 7 | Bit 8 |
| ----------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| Número 1    | 0     | 1     | 0     | 0     | 0     | 1     | 0     | 1     |
| Resultado 1 | 0     | 0     | 1     | 0     | 0     | 0     | 1     | 0     |
| Número 2    | 1     | 1     | 1     | 1     | 0     | 0     | 1     | 1     |
| Resultado 2 | 0     | 1     | 1     | 1     | 1     | 0     | 0     | 1     |
Y el resultado se inserta directo en la terminal, así en binario.
- **Left Shift($<<$)**: Lo que se hará será recorrer cada bit a la izquierda n pasos, generalmente se indica algo así: <<1, <<2, de forma que se sabe cuantos bits se recorrerán, aunque en este reto se dice al momento de hacer la pregunta.
Esta operación, solo se realiza en un número, en el reto se nos pide realizar esto con un solo salto, entonces se vería algo así:

| Números     | Bit 1 | Bit 2 | Bit 3 | Bit 4 | Bit 5 | Bit 6 | Bit 7 | Bit 8 |
| ----------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| Número 1    | 0     | 1     | 0     | 0     | 0     | 1     | 0     | 1     |
| Resultado 1 | 1     | 0     | 0     | 0     | 1     | 0     | 1     | 0     |
| Número 2    | 1     | 1     | 1     | 1     | 0     | 0     | 1     | 1     |
| Resultado 2 | 1     | 1     | 1     | 0     | 0     | 1     | 1     | 0     |
Y el resultado se inserta directo en la terminal, así en binario.

Hay que advertir algo, el resultado de la última operación nos solicitará moverlo a hexadecimal para obtener la flag. Un [conversor](https://toolbox.itsec.tamu.edu/#recipe=From_Base(2)To_Base(16)) puede ser de ayuda.

---
# Flag del reto
>picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_1367e2c6}

---
# Notas adicionales

---
# Referencias

