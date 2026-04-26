# Nombre del reto
>vault-door-3

---
# Descripción
>This vault uses for-loops and byte arrays.The source code for this vault is here: [VaultDoor3.java](https://challenge-files.picoctf.net/c_fickle_tempest/856cff883937e1cfe99e7e5b9c2fbbf08232a8135f919b1111615f007a4de03a/VaultDoor3.java)

---
# Solución
Se usó el siguiente script en python:
```python
target = "jU5t_a_sna_3lpm11g54e_u_4_m4r042"
flag = [''] * 32

# Replicamos la lógica del código Java para reconstruir el original
for i in range(0, 8):
    flag[i] = target[i]

for i in range(8, 16):
    flag[23-i] = target[i]

for i in range(16, 32, 2):
    flag[46-i] = target[i]

for i in range(31, 16, -2):
    flag[i] = target[i]

print("picoCTF{" + "".join(flag) + "}")
```

---
# Flag del reto
>picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_e45012}

---
# Notas adicionales

---
# Referencias

