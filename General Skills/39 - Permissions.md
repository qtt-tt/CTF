# Nombre del reto
>Permissions

---
# Descripción
>Can you read files in the root file?
>The system admin has provisioned an account for you on the main server:
>`ssh -p 56769 picoplayer@saturn.picoctf.net`
>Password: `33qE7mB5BF`
>Can you login and read the root file?

---
# Solución
Para este reto, nos dan como pista que debemos de ver los permisos que tenemos como usuario, de esta forma, debemos de usar el comando:
```bash
sudo -l
33qE7mB5BF
```
Al hacer esto, recibiremos lo siguiente: `(ALL) /usr/bin/vi`, esto nos dice: puedes usar la ruta /usr/bin/vi como superusuario, de forma que pues lo usamos, una vez que lo abrimos, nos abre un editor de texto, esto hará que podamos escapar al root para poder hacer cosas, usamos la opción `:!sh` y veremos que el prompt se volverá solo un #, entonces significa que somos root, ahora solo nos queda revisar.
```bash
cd /root
ls -la
cat .flag.txt
```

---
# Flag del reto
>picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}

---
# Notas adicionales

---
# Referencias

