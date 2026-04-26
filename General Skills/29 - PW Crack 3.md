# Nombre del reto
>

---
# Descripción
>Can you crack the password to get the flag?
>
>Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.
>
>There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

---
# Solución
Para este reto, deberemos desargar un total de 3 archivos con las líneas de comandos:
```bash
wget https://artifacts.picoctf.net/c/18/level3.py
wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
wget https://artifacts.picoctf.net/c/18/level3.hash.bin
```
Aquí podemos notar algo bastante interesante, y es que el 3er archivo tiene una terminación .hash, esto nos adelanta un poco la solución.
Si abrimos el archivo level3.py encontramos el siguiente script:
``` python
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")


level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]
```
Aquí encontramos otra cosa interesante, y es la biblioteca hash junto con 7 posibilidades. De aquí, nuestra solución se divide en 2:
## Solución 1: Fuerza bruta
Ya que tenemos las 7 posibilidades, podríamos ejecutar el script de python una y otra vez probando cada posibilidad, pero el problema de esto es que es muy lento incluso con las 7 posibilidades, pues en el peor de los casos, tendremos que probar las 7 y en el mejor de los casos, solo 1. Por lo que no es algo viable incluso en este caso.
## Solución 2: Comparación de hash
Ya que tenemos un archivo con terminación .hash, sabemos que se aplicó cierta operación hash sobre la respuesta correcta de la contraseña, por lo que al ver el archivo con la línea:
```
bvi level3.hash.bin
```
Nos resulta en un archivo "vacío" con un encabezado de: **16 02 6D 60 FF 9B 54 41 0B 34 35 B4 03 AF D2 26**, esto nos puede sonar de un bonito hexadecimal, pero si se intenta decodificar no podremos obtener nada interesante. Por lo que solo nos queda buscar un hash que tenga esa misma salida para encontrar la contraseña, recordemos que los hash no pueden tener espacios entre los caracteres hexadecimales, por lo que nos queda: **16026D60FF9B54410B3435B403AFD226**, con esto, podemos dar un vistazo rápido al script y ver que se aplica una función hash MD5 (`m = hashlib.md5()`) por lo que podemos entrar a cyberchef con cada contraseña posible para saber cual es la correcta.

- [8799](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=ODc5OQ) lo que nos da: e6051b3bfe716cc4a38c2f39ec199873
- [d3ab](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=ZDNhYg) lo que nos da: 2b268941ebe6a029484266060fa70243
- [1ea2](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=MWVhMg) lo que nos da: 8f60458cc64243ba3b88f8bfcfa269eb
- [acaf](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=YWNhZg) lo que nos da: 3df13964fd043dad82ac80b931a71f2d
- [2295](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=MjI5NQ) lo que nos da: **16026d60ff9b54410b3435b403afd226**
- [a9de](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=YTlkZQ) lo que nos da: b9cce7a7a688e9dbca3dd7f0469de54c
- [6f3d](https://toolbox.itsec.tamu.edu/#recipe=MD5()&input=NmYzZA) lo que nos da: cbdc1d56d54a78a5ba0543528f85af6a

Aquí encontramos nuestro mismo hash, por lo que ahora sabemos la contraseña.

---
# Flag del reto
>picoCTF{m45h_fl1ng1ng_6f98a49f}

---
# Notas adicionales
Antes de adivinar el tipo de hash, es mejor buscar en el código del encriptador, porque cuando buscaba el tipo estaba viendo la longitud, pero era mejor ver que función hash se estaba usando.

---
# Referencias
Se debió de buscar información sobre el [hash](https://chatgpt.com/share/6991f156-2870-800b-96a7-8e0a20419fa0).