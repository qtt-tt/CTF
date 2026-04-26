# Nombre del reto
>Special

---
# Descripción
>Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)
>Start your instance to see connection details.`ssh -p 56181 ctf-player@saturn.picoctf.net`
>The password is `d8819d45`

---
# Solución
Siendo sincero, no entendí mucho de como se resolvió este reto, tuve que buscar una explicación porque en un momento estuve atorado completamente, la pista no me ayudó mucho pero pude entrar. Al entrar primero vemos que special corrige todo, por ejemplo ls a is (lo cual no es un comando), entonces, se probó con un Clear, el cual al parecer limpiaba la pantalla y dejaba un shell limpio(?).

Entonces se optó por usar un & para hacer que la ejecución de dos acciones fueran hechas al mismo tiempo, por ejemplo, `Clear & find` el cual es para buscar archivos, una vez que vimos la ubicación del archivo, se usó lo mismo pero con cat y la ubicación para mostrar la flag.

---
# Flag del reto
>picoCTF{5p311ch3ck_15_7h3_w0r57_0c61d335}

---
# Notas adicionales
La verdad no entendí nada de este reto

---
# Referencias
Revisé la respuesta en el canal de [Martin Carlisle](https://youtu.be/6lEd1yVsxpw?si=fSgC7rZlnxmH_bjR).