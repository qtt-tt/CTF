# Nombre del reto
>ReadMyCert

---
# Descripción
>How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/424/readmycert.csr). 

---
# Solución
Para empezar, aquí se usará kali linux, ya que estaremos usando ciertos comandos.
Primero vemos el tipo de archivo que es.
```bash
file readmycert.csr
```
Luego lo abriremos
```bash
openssl req -in readmycert.csr -noout -text
```
Y con esto nos dará la bandera

---
# Flag del reto
>picoCTF{read_mycert_5aeb0d4f}

---
# Notas adicionales

---
# Referencias

