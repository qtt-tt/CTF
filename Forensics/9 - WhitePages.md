# Nombre del reto
>WhitePages

---
# Descripción
>I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/3ba37d6bee0d96d5e3783ba94da753407f9168b61d796797f0816db5aaa86136/whitepages.txt) is all blank!

---
# Solución
Para esta solución se debió de instalar pwntools para python se puede usar este comando:
```bash
 sudo apt install python3-pwntools
```
Ahora, podemos crear un script de python que nos resuelva el reto
```python
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83', b'0')
data = data.replace(b'\x20', b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)
```
Al ejecutarlo, esto nos dará la flag.

---
# Flag del reto
>picoCTF{not_all_spaces_are_created_equal_f62118c302bc9c9791e81915c805af3d}

---
# Notas adicionales

---
# Referencias

