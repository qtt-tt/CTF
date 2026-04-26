# Nombre del reto
>Chrono

---
# Descripción
>How to automate tasks to run at intervals on linux servers?Use ssh to connect to this server:

```text
Server: saturn.picoctf.net
Port: 50188
Username: picoplayer 
Password: kZx-HVJKu8
```

---
# Solución
Para este reto, deberemos de saber un poco donde se encuentran las configuraciones o tareas que se ejecutan cada cierto tiempo, por lo que deberemos hacer algo así:
```bash
ssh picoplayer@saturn.picoctf.net -p 50188
kZx-HVJKu8
cat /etc/crontab
```
Aquí, lo que se hace es acceder a la carpeta de configuraciones de tiempos del usuario picoplayer, una vez que hacemos el cat, el sistema nos muestra nuestra flag.

---
# Flag del reto
>picoCTF{Sch3DUL7NG_T45K3_L1NUX_5b7059d0}

---
# Notas adicionales

---
# Referencias

