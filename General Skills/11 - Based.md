# Nombre del reto
>Based

---
# Descripción
>To get truly 1337, you must understand different data encodings, such as hexadecimal or binary.
>
>Can you get the flag from this program to prove you are on the way to becoming 1337?
>
>Connect with nc fickle-tempest.picoctf.net 60709.

---
# Solución
# Solución 1: Cyberchef separado
La solución a este reto es un poco complicada, ya que para esto nos pide en la descripción saber de temas de binarios o hexadecimal, pero desglosemos poco a poco.
Este reto nos pide ejecutar una instancia, conectándonos con un netcat a un servidor a través de un puerto (hay que aclarar que el puerto cambia cada vez, entonces esto no es una solución absoluta, es el proceso de pensamiento para resolverlo). Una vez que nos conectamos encontramos un mensaje como lo sería:
`Please give the 01110011 01101111 01100011 01101011 01100101 01110100 as a word.`
Por sus variantes de números entre 0 y 1, sabemos que es binario, por lo que en cyberchef podemos introducirlo fácilmente. Por lo que la solución puede encontrarse [aquí](https://toolbox.itsec.tamu.edu/#recipe=From_Binary('Space',8)&input=MDExMTAwMTEgMDExMDExMTEgMDExMDAwMTEgMDExMDEwMTEgMDExMDAxMDEgMDExMTAxMDA) dándonos **socket**. Después nos dará otro mensaje:
`Please give me the  o160 o151 o145 as a word.`
Aquí estuvo un poco descifrarlo ya que era un formato de encriptación que nunca se había visto, por lo que se recurrió a una investigación rápida sobre su formato, dando que era formato de octal, por lo que se procede a desencriptarlo igual con cyberchef, su solución se puede encontrar [aquí](https://toolbox.itsec.tamu.edu/#recipe=From_Octal('Space')&input=MTYwIDE1MSAxNDU) (aunque hay que hacer la aclaración que se debe de borrar la o de cada número) dándonos la palabra **pie**. Después nos dará otro mensaje:
`Please give me the 6c697a617264 as a word.`
Aunque esta cadena es un poco rara de encontrar, podemos notar que solo hay números y dos letras minúsculas (a y c), entonces, lo más posible es que fuera hexadecimal sin espacios, por lo que se intenta en cyberchef, el intento se encuentra [aquí](https://toolbox.itsec.tamu.edu/#recipe=From_Hex('Auto')&input=NmM2OTdhNjE3MjY0) y nos da la palabra **lizard**. Posteriormente nos resulta la flag de este reto.
## Solución 2: Cyberchef junto
Esto más que otra forma de solucionarlo, puede ser una forma de prepararse para este reto, y es usar la siguiente página de [cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Octal('Space'/disabled)From_Binary('Space',8/disabled)From_Hex('Auto')&input=NmM2OTdhNjE3MjY0) en la cual encontramos las recetas requeridas, solamente a la hora de desencriptar cada uno, se habilita la receta (con un click en el símbolo de prohibido) para usarla.

---
# Flag del reto
>picoCTF{learning_about_converting_values_563BAF26}

---
# Notas adicionales

---
# Referencias

Para la información de la representación de [Octal](https://chatgpt.com/share/698a704b-bbd8-800b-9fcb-6487098bf7c1) se recurrió a una pequeña ayuda de la IA.