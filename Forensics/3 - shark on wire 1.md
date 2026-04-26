# Nombre del reto
>shark on wire 1

---
# Descripción
>We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/134d2a2cf6ec5b7e757effc9b32977af7cc324b8e99a5ddb64737794a14dc18d/capture.pcap). Recover the flag.

---
# Solución
Para esta solución, debemos de entrar a wireshark, donde abriremos nuestro archivo descargado (con extensión .pcap), aquí encontraremos un montón de lineas, pero nos importarán las de protocolo UDP, para esto le daremos a seguir el stream buscando, empezaremos en el stream 4 donde no hay nada, en el stream 5 hay pico repetido muchas veces, y en el 6 encontraremos nuestra flag.

---
# Flag del reto
>picoCTF{StaT31355_636f6e6e}

---
# Notas adicionales

---
# Referencias
[¿Qué $#&@ es wireshark?](https://chatgpt.com/share/69ac9cb9-2460-800b-be0e-39a3e38a5c78).
[¿Qué $#&@ son los protocolos de red?](https://chatgpt.com/share/69ac9d1a-0ce4-800b-bd99-4cc0c0bde63c).