# Nombre del reto
>First Find

---
# Descripción
>Unzip this archive and find the file named 'uber-secret.txt'
>
>[Download zip file](https://artifacts.picoctf.net/c/501/files.zip)

---
# Solución
Para la búsqueda, como sabemos el nombre del archivo podemos entrar directamente a los directorios con el comando **find**, la estructura de su uso es algo como: `find DONDE_BUSCAR -name "nombre"`, de esta forma, podemos encontrar la flag.
La forma de resolverlo fue la siguiente:
```bash
wget https://artifacts.picoctf.net/c/501/files.zip
unzip files.zip
find files -name "uber-secret.txt"
cat files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

---
# Flag del reto
>picoCTF{f1nd_15_f457_ab443fd1}

---
# Notas adicionales

---
# Referencias

