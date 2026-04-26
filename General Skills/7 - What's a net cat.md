# Nombre del reto
>What's a net cat?

---
# Descripción
>Using netcat (nc) is going to be pretty important. Can you connect to fickle-tempest.picoctf.net at port 58734 to get the flag?

---
# Solución
## Solución 1: conexión con nc en Linux
nc (o netcat) es una forma de conectarte a un servidor a través de un puerto, su sintaxis es: **nc *servidor* *puerto*** de forma que, el proceso para resolver este reto fue primero que nada comenzar a correr la instancia que se encuentra en el mismo reto, después, conectarse al servidor con el puerto. Esto me llevó a una mini ventana que contenía la flag.
```bash
nc fickle-tempest.picoctf.net 58734
```

---
# Flag del reto
>picoCTF{nEtCat_Mast3ry_f20a728c}

---
# Notas adicionales
nc se usa para conectarse a un servicio remoto desde la terminal.

---
# Referencias

