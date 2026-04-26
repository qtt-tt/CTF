# Nombre del reto
>Magikarp Ground Mission

---
# Descripción
>Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin.
>
>Login via `ssh` as **ctf-player** with the password, **8c606eb1** on the host **wily-courier.picoctf.net** and port **53241**.

---
# Solución
Se nos solicita conectarnos via ssh a un servidor en el cual estaremos practicando el como movernos entre directorios. Tras conectarnos al servidor vemos el directorio al que hemos entrado, nos encontramos con dos documentos de texto, al leer el primero nos da una parte de la flag (picoCTF{xxsh_), en el segundo nos pide que vayamos al directorio raíz donde encontramos la 2da parte de la flag (0ut_0f_//4t3r_) e instrucciones para llegar a la 3ra parte, pidiendo que vayamos al home del usuario, encontrando la tercera parte de la flag (0b24fc4f}). Completando este reto de la siguiente manera:
```bash
ssh ctf-player@wily-courier.picoctf.net -p 53241
ls
cat 1of3.flag.txt
cat instructions-to-2of3.txt 
cd /
ls
cat 2of3.flag.txt
cat instructions-to-3of3.txt 
cd ~
ls
cat 3of3.flag.txt
exit
```

---
# Flag del reto
>picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}

---
# Notas adicionales

---
# Referencias

