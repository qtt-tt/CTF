# Nombre del reto
>Static ain't always noise

---
# Descripción
>Can you look at the data in this binary? The bash script might help!
>
>[static](https://challenge-files.picoctf.net/c_wily_courier/34dfb62cf2c94a618c7cdc292ff1c4062b104773695071e9a16ab25ad8cc935c/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/34dfb62cf2c94a618c7cdc292ff1c4062b104773695071e9a16ab25ad8cc935c/ltdis.sh)

---
# Solución
## Solución 1: Ejecución del archivo bash
Para empezar, nos dan dos archivos, uno que es un archivo binario y otro que es un archivo bash, el cual tras haberlo analizado, nos damos cuenta que nos ayuda a analizar archivos binarios. Para empezar, el archivo ltdis.sh fue hecho ejecutable con el comando:  `chmod +x ltdis.sh` para después pasar el archivo binario como argumento del bash, resultando en algo así:
```bash
chmod +x ltdis.sh
./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
```
Esto nos resulta en dos archivos, uno que contiene el desensamblaje del binario (en static.ltdis.x86_64.txt) y el otro las palabras que fueron encontradas (static.ltdis.strings.txt). Para finalizar, podemos leer las líneas de este último archivo usando grep para buscar algún patrón de texto.
```bash
strings static.ltdis.strings.txt | grep picoCTF
3020 picoCTF{d15a5m_t34s3r_20335e41}
```
Obteniendo así la flag.

---
# Flag del reto
>picoCTF{d15a5m_t34s3r_20335e41}

---
# Notas adicionales

---
# Referencias

