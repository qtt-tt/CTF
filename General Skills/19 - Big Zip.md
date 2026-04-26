# Nombre del reto
>Big Zip

---
# Descripción
>Unzip this archive and find the flag.
>
>[Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)

---
# Solución
Para iniciar debemos de recurrir a la forma recursiva del comando grep, el cual se escribe de la siguiente forma: `grep -r "patronTexto" carpeta` de modo que, como su nombre lo dice, al extraer las carpetas del zip grande (big-zip-files) podremos revisar todas las carpetas. Se usaron los siguientes comandos:
```bash
wget https://artifacts.picoctf.net/c/505/big-zip-files.zip
unzip big-zip-files.zip
grep -r "picoCTF{" big-zip-files
```


---
# Flag del reto
>picoCTF{gr3p_15_m4g1c_ef8790dc}

---
# Notas adicionales

---
# Referencias

