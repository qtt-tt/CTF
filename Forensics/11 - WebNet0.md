# Nombre del reto
>WebNet0

---
# Descripción
>We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key). Recover the flag.

---
# Solución
Descargar el .pcap y usar la key que se nos da para el encriptado TLS para con ello poder conseguir la flag
Primero debemos descargar el .pcap y la key, después debemos de usar Wireshark, con el le introducimos que maneje para el flujo de las TLS la key que se nos dio, para que con ello podamos desencriptar la información, luego de eso solamente hacemos una búsqueda de detalles de paquetes con picoCTF y con eso obtenemos la flag

---
# Flag del reto
>picoCTF{nongshim.shrimp.crackers}

---
# Notas adicionales

---
# Referencias

