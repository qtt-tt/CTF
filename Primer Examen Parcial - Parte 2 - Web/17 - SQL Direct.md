# Nombre del reto
>SQL Direct

---
# Descripción
>Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 55505 -U postgres pico` Password is `postgres`

---
# Solución
Primero es usar el webshell, después entramos con las credenciales que nos da, luego utilizamos \list para poder ver las distintas bases de datos que hay y usamos \c pico para entrar a la de pico, luego con \dt flags revisamos el esquema de las flags y por último usamos una sentencia sql "select * from flags;" para con ello obtener la flag

---
# Flag del reto
>picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}

---
# Notas adicionales

---
# Referencias

