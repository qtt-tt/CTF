# Nombre del reto
>Mind your Ps and Qs

---
# Descripción
>In RSA, a small e value can be problematic, but what about N? Can you decrypt this?[values](https://challenge-files.picoctf.net/c_wily_courier/8f75844947ccdb93020eecaf5eea8be97753b2075202328032bb4854ca7c6863/values)

---
# Solución
Para esta solución usaremos esta [herramienta](https://www.dcode.fr/rsa-cipher) que nos sirve para decodificar nuestros valores (en este caso fueron los siguientes):
```
c: 15341890103764929939105506004034128738090325640037083301857608662849501626260517
n: 948406957756830799684818171639547165784816468744946013083947881743680617123566349
e: 65537
```
Pero pasó algo raro, nos dio la cadena invertida, por lo que la introduciremos en un [reversador de texto](https://www.dcode.fr/reverse-writing)

---
# Flag del reto
>picoCTF{sma11_N_n0_g0od_1dc7ae91}

---
# Notas adicionales

---
# Referencias

