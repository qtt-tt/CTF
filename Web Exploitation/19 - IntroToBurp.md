# Nombre del reto
>IntroToBurp

---
# Descripción
>Try [here](http://titan.picoctf.net:52105/) to find the flag

---
# Solución
Para empezar, deberemos de llenar el registro que aparece, al llegar a la validación en 2 pasos, aquí no tenemos nuestro código que nos ayude a ingresar. Para lograr entrar, activamos nuestro proxy de foxyproxy y empezamos a interceptar con burpsuite, al mandar una solicitud, deberemos de eliminar el parámetro otp para darle un error a la página, la cual nos dará nuestra flag.

---
# Flag del reto
>picoCTF{#0TP_Bypvss_SuCc3$S_b3fa4f1a}

---
# Notas adicionales

---
# Referencias

