# Nombre del reto
>PW Crack 2

---
# Descripción
>Can you crack the password to get the flag?
>
>Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

---
# Solución
Este reto nos pide encontrar la contraseña de un archivo, para esto, primero debemos descargar ambos archivos:
```bash
wget https://artifacts.picoctf.net/c/12/level1.py
wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
```
Una vez que los hemos descargado, ejecutamos el archivo level1.py, esto nos arroja la siguiente salida:
```bash
python3 level2.py
Please enter correct password for flag:
```
Como no sabemos la contraseña, debemos de buscar dentro de ambos archivos.

El archivo level2.flag.txt.enc es un archivo binario, por lo que no lo abriremos de inmediato a menos que sea necesario.

El archivo level2.py es un script de python que contiene lo siguiente:
```python
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

flag_enc = open('level2.flag.txt.enc', 'rb').read()

def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")

level_2_pw_check()
```
Los comentarios nos dicen que la función str_xor no nos servirá para encontrar la bandera, pero si vamos hacia abajo encontramos una condicional, diciendo que debemos de introducir la cadena: **chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)**. Esto podría ser un problema, pero aquí tenemos de dos para conseguir la contraseña:
- Correr esa línea en python, ya que la función chr() forma parte de su lenguaje
- Usar [cyberchef](https://toolbox.itsec.tamu.edu/#recipe=From_Hex('Auto')&input=MHg2NCAweDY1IDB4MzcgMHgzNg) para resolverlo
Una vez que encontramos la flag (la cual es de76) solamente nos queda introducirla cuando el archivo nos pregunta una contraseña, esto nos resulta en la flag.

---
# Flag del reto
>picoCTF{tr45h_51ng1ng_489dea9a}

---
# Notas adicionales

---
# Referencias

