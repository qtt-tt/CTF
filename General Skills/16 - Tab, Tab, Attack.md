# Nombre del reto
>Tab, Tab, Attack

---
# Descripción
>Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.
>
>[Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/c090282eec93405912f926586287741dd5b9bd24cbdf8f3555c53902d556e508/Addadshashanammu.zip)

---
# Solución
Para este reto, se necesita hacer uso de la tabulación para navegar entre directorios con un nombre extenso y complicado de escribir, tras esto, no hay mucho misterio, pues tras llegar al repositorio más profundo encontramos dos archivos, uno ejecutable. Se ejecutó y nos resultó en la flag.
```bash
unzip Addadshashanammu.zip
cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
ls
./fang-of-haynekhtnamet 
```

---
# Flag del reto
>picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}

---
# Notas adicionales

---
# Referencias

