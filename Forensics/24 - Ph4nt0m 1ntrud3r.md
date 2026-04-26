# Nombre del reto
>Ph4nt0m 1ntrud3r

---
# Descripción
>A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.

---
# Solución
Primero descargamos el .pcap, después al abrirlo con wireshark podemos observar que si filtramos por tiempos, se va formando una cadena que es la flag encriptada, por lo que para conseguirla de manera automática, utilizamos el comando de "tshark -r myNetworkTraffic.pcap -T fields -e frame.time_epoch -e tcp.payload | sort -n | awk '{print $2}' | tr -d '\n' | xxd -r -p | base64 -d" y con ello obtenemos la flag

---
# Flag del reto
>picoCTF{1t_w4snt_th4t_34sy_tbh_4r_d1065384}

---
# Notas adicionales

---
# Referencias

