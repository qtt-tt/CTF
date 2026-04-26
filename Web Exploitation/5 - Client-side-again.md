# Nombre del reto
>Client-side-again

---
# Descripción
>Can you break into this super secure portal?
>[http://fickle-tempest.picoctf.net:57556](http://fickle-tempest.picoctf.net:57556)

---
# Solución
Para resolver este reto, debemos de saber un poco del nicify, pues en el código de la página encontramos un pedazo ilegible directamente, algo así:
```java script
var _0x5a46=['daf93}','_again_4','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];(function(_0x4bd822,_0x2bd6f7){var _0xb4bdb3=function(_0x1d68f6){while(--_0x1d68f6){_0x4bd822['push'](_0x4bd822['shift']());}};_0xb4bdb3(++_0x2bd6f7);}(_0x5a46,0x1b3));var _0x4b5b=function(_0x2d8f05,_0x4b81bb){_0x2d8f05=_0x2d8f05-0x0;var _0x4d74cb=_0x5a46[_0x2d8f05];return _0x4d74cb;};function verify(){checkpass=document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];split=0x4;if(checkpass[_0x4b5b('0x2')](0x0,split*0x2)==_0x4b5b('0x3')){if(checkpass[_0x4b5b('0x2')](0x7,0x9)=='{n'){if(checkpass[_0x4b5b('0x2')](split*0x2,split*0x2*0x2)==_0x4b5b('0x4')){if(checkpass[_0x4b5b('0x2')](0x3,0x6)=='oCT'){if(checkpass[_0x4b5b('0x2')](split*0x3*0x2,split*0x4*0x2)==_0x4b5b('0x5')){if(checkpass['substring'](0x6,0xb)=='F{not'){if(checkpass[_0x4b5b('0x2')](split*0x2*0x2,split*0x3*0x2)==_0x4b5b('0x6')){if(checkpass[_0x4b5b('0x2')](0xc,0x10)==_0x4b5b('0x7')){alert(_0x4b5b('0x8'));}}}}}}}}else{alert(_0x4b5b('0x9'));}}

```
Entonces, se agrega en un [nicfier](http://jsnice.org/) de java script, para poder ver un poco mejor la forma de nuestro código, pero nos regresa otro monstro gigante (al menos para mi que no se tanto Java Script):
```java script
/** @type {Array} */
var _0x5a46 = ["daf93}", "_again_4", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
(function(paths, opt_attributes) {
  /**
   * @param {number} val
   * @return {undefined}
   */
  var setter = function(val) {
    for (;--val;) {
      paths["push"](paths["shift"]());
    }
  };
  setter(++opt_attributes);
})(_0x5a46, 435);
/**
 * @param {string} key
 * @param {?} dataAndEvents
 * @return {?}
 */
var _0x4b5b = function(key, dataAndEvents) {
  /** @type {number} */
  key = key - 0;
  var label = _0x5a46[key];
  return label;
};
/**
 * @return {undefined}
 */
function verify() {
  checkpass = document[_0x4b5b("0x0")]("pass")[_0x4b5b("0x1")];
  /** @type {number} */
  split = 4;
  if (checkpass[_0x4b5b("0x2")](0, split * 2) == _0x4b5b("0x3")) {
    if (checkpass[_0x4b5b("0x2")](7, 9) == "{n") {
      if (checkpass[_0x4b5b("0x2")](split * 2, split * 2 * 2) == _0x4b5b("0x4")) {
        if (checkpass[_0x4b5b("0x2")](3, 6) == "oCT") {
          if (checkpass[_0x4b5b("0x2")](split * 3 * 2, split * 4 * 2) == _0x4b5b("0x5")) {
            if (checkpass["substring"](6, 11) == "F{not") {
              if (checkpass[_0x4b5b("0x2")](split * 2 * 2, split * 3 * 2) == _0x4b5b("0x6")) {
                if (checkpass[_0x4b5b("0x2")](12, 16) == _0x4b5b("0x7")) {
                  alert(_0x4b5b("0x8"));
                }
              }
            }
          }
        }
      }
    }
  } else {
    alert(_0x4b5b("0x9"));
  }
}
;
```
Ahora, esta solución se divide en dos posibles caminos, o verificas cada if para encontrar que va con que, o la armamos con lógica según el arreglo 0x5a46, entonces, vamos con la parte del arreglo.

Contamos con las siguientes posiciones:


| Posición |   0    |    1     |  2   |         3         |         4          |       5        |   6   |     7     |    8     |    9     |
| :------: | :----: | :------: | :--: | :---------------: | :----------------: | :------------: | :---: | :-------: | :------: | :------: |
|  Valor   | daf93} | _again_4 | this | Password Verified | Incorrect password | getElementById | value | substring | picoCTF{ | not_this |
Ahora, si revisamos los valores que puede tener cada posición, nos damos cuenta que hay algunas que son palabras que usa la página, como las posiciones: 3, 4, 5, 6 y 7, por lo que nuestras opciones para armar la flag son:

|   0    |    1     |  2   |    8     |    9     |
| :----: | :------: | :--: | :------: | :------: |
| daf93} | _again_4 | this | picoCTF{ | not_this |
Ahora, si existen 5 opciones y pudieran ir en cualquier orden, encontraríamos al menos 120 soluciones posibles, pero se nos recorta al saber que podemos resolverlo con lógica:
- La posición 8 debe de ir primero, por que cualquier flag empieza con picoCTF{
- La posición 0 debe de ir al final, porque cualquier flag termina con una llave de cierre (})
- La posición 1 debe de ir después de otra posición, pues es poco probable que la flag inicie con un guión bajo; ya que generalmente simbolizan espacios para dejar mensajes.
	- Además que es más posible que vaya antes de la 8, ya que el 4 con daf93 suena a algo que existiría en picoCTF como flag, ya que la mayoría son encriptadas.
- Las posición 9 y 1 pueden ser la que empiece ya que si la pensamos con las anteriores pistas, estas tienen una posibilidad de tener algún mensaje.
Ahora, si tomamos en cuenta esto, encontramos solo dos flags posibles:
- picoCTF{not_this_again4daf93}
- picoCTF{this_again4daf93}
Ahora solo nos queda probar nuestras teorías y encontrar cual es la verdadera flag.
---
# Flag del reto
>picoCTF{not_this_again_4daf93}

---
# Notas adicionales

---
# Referencias

