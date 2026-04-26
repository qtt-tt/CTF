# Nombre del reto
>Operation Orchid

---
# Descripción
>Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/212/disk.flag.img.gz)

---
# Solución
Primero descargamos el archivo que se nos da y lo descomprimimos, después lo empezamos a analizar las particiones y vemos la última, luego al llegar a "fls disk.flag.img -o 411648 472" podemos observar que aqui se encuentra la flag pero que la encriptaron, por lo que la pasamos a nuestra maquina usando "icat disk.flag.img -o 411648 1782 > flag.txt.enc", después solamente desencriptamos la flag usando "openssl aes256 -d -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567" y con ello obtenemos la flag

---
# Flag del reto
>picoCTF{h4un71ng_p457_0a710765}

---
# Notas adicionales

---
# Referencias

