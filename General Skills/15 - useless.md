# Nombre del reto
>useless

---
# Descripción
>There's an interesting script in the user's home directoryThe work computer is running SSH. 
>
>We've been given a script which performs some basic calculations, explore the script and find a flag.

```
Hostname: saturn.picoctf.net
Port:     58721
Username: picoplayer
Password: password
```

---
# Solución
Para este reto, se nos solicita usar el comando ssh de linux para conectarnos a cierto servidor, en cierto puerto, con cierto usuario, el comando usado fue:
```bash
ssh -p 58721 picoplayer@saturn.picoctf.net
```
Para continuar nos pregunta si confiamos en este servidor y decimos que si, por lo que nos pedirá la contraseña. Al ser ingresada nuestro prompt pasa a ser del usuario en el servidor, ahora, la descripción nos dice que hay un archivo interesante, por lo que realizamos un comando `ls` para ver el nombre del archivo, al ser capaz de ejecutarse, se lanzó una ejecución.
```bash
picoplayer@challenge:~$ ./useless
Read the code first
```
Para esto, se hizo un cat al archivo dándonos el siguiente código:
```bash
#!/bin/bash
# Basic mathematical operations via command-line arguments

if [ $# != 3 ]
then
  echo "Read the code first"
else
        if [[ "$1" == "add" ]]
        then 
          sum=$(( $2 + $3 ))
          echo "The Sum is: $sum"  

        elif [[ "$1" == "sub" ]]
        then 
          sub=$(( $2 - $3 ))
          echo "The Substract is: $sub" 

        elif [[ "$1" == "div" ]]
        then 
          div=$(( $2 / $3 ))
          echo "The quotient is: $div" 

        elif [[ "$1" == "mul" ]]
        then
          mul=$(( $2 * $3 ))
          echo "The product is: $mul" 

        else
          echo "Read the manual"
         
        fi
fi
```
Nos dice que leamos el manual, por lo tanto nos adentramos haciendo uso de man. Este nos resulta en información del programa y, nuestra flag.
```bash
picoplayer@challenge:~$ man useless

useless
     useless, -- This is a simple calculator script

SYNOPSIS
     useless, [add sub mul div] number1 number2

DESCRIPTION
     Use the useless, macro to make simple calulations like addition,subtraction, multiplication and division.

Examples
     ./useless add 1 2
       This will add 1 and 2 and return 3

     ./useless mul 2 3
       This will return 6 as a product of 2 and 3

     ./useless div 6 3
       This will return 2 as a quotient of 6 and 3

     ./useless sub 6 5
       This will return 1 as a remainder of substraction of 5 from 6

Authors
     This script was designed and developed by Cylab Africa

     picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_5136}

```

---
# Flag del reto
>picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_5136}

---
# Notas adicionales

---
# Referencias
La información básica del comando ssh se encuentra [aquí](https://chatgpt.com/share/698be499-5af0-800b-a284-ea4e3a67e89a).
