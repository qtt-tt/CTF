# Nombre del reto
>shark on wire 2

---
# Descripción
>

---
# Solución
Para este reto deberemos de buscar cierta comunicación entre los paquetes que nos proporciona el reto, encontramos que hay algunos paquetes UDP que llevan cierto parecido con la bandera, pero no se encontró cual es el bueno.

Debemos de instalar scapy:
```bash
sudo apt install python3-scapy
```

Encontramos el puerto al que se van (22) y encontramos que la información corresponde a algunas letras, por lo que podemos usar el siguiente script:
```python
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag += chr(p[UDP].sport-5000)
			
print(flag)
```

---
# Flag del reto
>picoCTF{p1LLf3r3d_data_v1a_st3g0}

---
# Notas adicionales

---
# Referencias

