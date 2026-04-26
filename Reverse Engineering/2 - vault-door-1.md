# Nombre del reto
>vault-door-1

---
# Descripción
>This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: VaultDoor1.java

---
# Solución
Usé el siguiente comando:
```bash
cat flag | grep "charAt" | sed "s/.*charAt(\([0-9]*\)).*'\([^']*\)'.*/\1 \2/" | sort -n | awk '{print $2}' | tr -d '\n'
```
O se puede usar también:
```bash
cat VaultDoor1.java | grep "charAt" | sed "s/.*charAt(\([0-9]*\)).*'\([^']*\)'.*/\1 \2/" | sort -n | awk '{print $2}' | tr -d '\n'
```
---
# Flag del reto
>picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_a4d736}

---
# Notas adicionales

---
# Referencias

