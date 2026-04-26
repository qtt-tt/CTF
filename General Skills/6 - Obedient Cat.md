# Nombre del reto
>Obedient Cat

---
# Descripción
>This file has a flag in plain sight (aka "in-the-clear").
>
>[file(este link lo descarga)](https://challenge-files.picoctf.net/c_wily_courier/8d63e440ec205416efd07e5c9f9ea0ab050fe3f4c8fc30bebfcca22f0c902491/flag)

---
# Solución
## Solución 1: comando cat en Linux
El comando cat nos permite ver el contenido de uno o varios archivos, de modo que en este caso se siguió el siguiente proceso:
```bash
wget https://challenge-files.picoctf.net/c_wily_courier/8d63e440ec205416efd07e5c9f9ea0ab050fe3f4c8fc30bebfcca22f0c902491/flag
cat flag
```
## Solución 2: comando grep en Linux
Aunque el comando cat nos ayuda a ver el contenido de un archivo, podemos buscar el patrón de la bandera en el archivo siguiendo el siguiente proceso:
```bash
wget https://challenge-files.picoctf.net/c_wily_courier/8d63e440ec205416efd07e5c9f9ea0ab050fe3f4c8fc30bebfcca22f0c902491/flag
grep picoCTF flag
```
## Solución 3: comando less en Linux
Otro comando útil a la hora de leer archivos es el comando less, el cual abre un visualizador de archivos en la propia terminal, de modo que para resolverlo usando este comando (aprovechando que tiene una sola linea) es el siguiente:
```bash
wget https://challenge-files.picoctf.net/c_wily_courier/8d63e440ec205416efd07e5c9f9ea0ab050fe3f4c8fc30bebfcca22f0c902491/flag
less flag
```

---
# Flag del reto
>picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}

---
# Notas adicionales

---
# Referencias

