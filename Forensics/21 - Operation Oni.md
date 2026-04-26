# Nombre del reto
>Operation Oni

---
# Descripción
>Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/71/disk.img.gz)
- Remote machine: `ssh -i key_file -p 56064 ctf-player@saturn.picoctf.net`

---
# Solución
Primero descargamos el archivo que se nos da y lo descomprimimos, luego analizandolo podemos ver que contiene una llave ssh, por lo que la copiamos con "icat -o 206848 disk.img 2345 > id_ed25519", después nos damos permisos con esa misma llave con "chmod 600 id_ed25519" y luego de ello entramos a la página y cambiamos el apartado de key_file con nuestra nueva llave, entramos y aplicamos un "cat flag.txt" y con ello obtenemos la flag

---
# Flag del reto
>picoCTF{k3y_5l3u7h_af277f77}

---
# Notas adicionales

---
# Referencias

