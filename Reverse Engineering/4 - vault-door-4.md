# Nombre del reto
>vault-door-4

---
# Descripción
>This vault uses ASCII encoding for the password.
>The source code for this vault is here: VaultDoor4.java

---
# Solución
Se usó la siguiente linea:
```bash
python3 -c "print(''.join([chr(x) for x in [106, 85, 53, 116, 95, 52, 95, 98, 0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f, 0o142, 0o131, 0o164, 0o63, 0o163, 0o137, 0o142, 0o64]] ) + 'e943c3a0')"
```

---
# Flag del reto
>picoCTF{jU5t_4_bUnCh_0f_bYt3s_b4e943c3a0}

---
# Notas adicionales

---
# Referencias

