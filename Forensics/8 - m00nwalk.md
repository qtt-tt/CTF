# Nombre del reto
>m00nwalk

---
# Descripción
>Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav) from the moon.

---
# Solución
Descargaremos la herramienta para hacer uso del sstv, tras descargarla haremos lo siguiente:
```bash
wget https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav
sstv -d message.wav -o result.png
```
Nuestra imagen estará volteada, por lo que solo hay que girarla con el editor de imágenes de kali y con eso se nos mostrará la imagen.

---
# Flag del reto
>picoCTF{beep_boop_im_in_space}

---
# Notas adicionales

---
# Referencias

[Mensajes desde la luna](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa2F2ZjhWWjY5SXdSNGdwdThQa2dUY0N3TG90QXxBQ3Jtc0ttSUZDN05SNlFadzkwaXdiRFN6UTNDOXNJMWdVckxhUHE0VFVzLVpibHdKOG5WV25Wa3JsbVpWWEFqeDQxbFJYMHJZdTllS1VFa3VWdG1HdkZGYTNhNU9Ed0dUVmNsdW1Nc05NalJ3RkdOdE5VdUpXVQ&q=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FApollo_11_missing_tapes&v=UyLTEpAz6eE).
[Herramienta](https://github.com/colaclanth/sstv).