# Nombre del reto
>Super SSH

---
# Descripción
>Using a Secure Shell (SSH) is going to be pretty important.
>
>Can you ssh as ctf-player to titan.picoctf.net at port 56264 to get the flag?
>
>You'll also need the password 6dd28e9b. If asked, accept the fingerprint with yes.
>
>If your device doesn't have a shell, you can use: https://webshell.picoctf.org
>
>If you're not sure what a shell is, check out our Primer: https://primer.picoctf.com/#_the_shell

---
# Solución
Este reto nos hace lanzar una instancia, al lanzarla se nos pide conectarnos a cierto servidor con cierto usuario con cierto puerto e ingresar la contraseña, los comandos usados fueron:
```bash
ssh ctf-player@titan.picoctf.net -p 56264
```
Para la contraseña, se copia y pega, recordando que las contraseñas son invisibles en linux, entonces nos arroja la línea: **Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}** y obtuvimos así la flag.

---
# Flag del reto
>picoCTF{s3cur3_c0nn3ct10n_5d09a462}

---
# Notas adicionales

---
# Referencias
Información sobre la línea de comandos usada: [ssh](https://chatgpt.com/share/699164a6-e1c0-800b-a35e-91670a61746a)

