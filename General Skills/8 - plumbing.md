# Nombre del reto
>plumbing

---
# Descripción
>Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?
>
>Connect to fickle-tempest.picoctf.net 64542.

---
# Solución
# Solución 1: netcat unido con grep
En este reto nos introducen el pipeline (|) el cual nos permite que, el primer comando se ejecute y su resultado se use como entrada en el siguiente, de esta forma primero se probó al conectarse al servicio y puerto indicado, esto me dio un conjunto gigante de líneas, por lo que se unió el comando con un grep para buscar el patrón de la flag, esto nos resultó una sola línea con la flag.
```bash
nc fickle-tempest.picoctf.net 64542 | grep picoCTF
```

---
# Flag del reto
>picoCTF{digital_plumb3r_11fffFE5}

---
# Notas adicionales

---
# Referencias

