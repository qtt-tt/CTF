# Nombre del reto
>Scavenger Hunt

---
# Descripción
>There is some interesting information hidden around this site. Can you find it?
>[http://wily-courier.picoctf.net:49602/](http://wily-courier.picoctf.net:49602/)

---
# Solución
Al entrar a la página, encontramos que se parece al reto [[4 - where are the robots]] en el cual, tenemos que entrar a varias partes del código, primero el html:
```html

<!doctype html>
<html>
  <head>
    <title>Scavenger Hunt</title>
    <link href="https://fonts.googleapis.com/css?family=Open+Sans|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="mycss.css">
    <script type="application/javascript" src="myjs.js"></script>
  </head>

  <body>
    <div class="container">
      <header>
		<h1>Just some boring HTML</h1>
      </header>

      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>
      <button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>

      <div id="tabintro" class="tabcontent">
		<h3>How</h3>
		<p>How do you like my website?</p>
      </div>

      <div id="tababout" class="tabcontent">
		<h3>What</h3>
		<p>I used these to make this site: <br/>
		  HTML <br/>
		  CSS <br/>
		  JS (JavaScript)
		</p>
	<!-- Here's the first part of the flag: picoCTF{t -->
      </div>

    </div>

  </body>
</html>
```
Después, entramos a la página del css:
```css
div.container {
    width: 100%;
}

header {
    background-color: black;
    padding: 1em;
    color: white;
    clear: left;
    text-align: center;
}

body {
    font-family: Roboto;
}

h1 {
    color: white;
}

p {
    font-family: "Open Sans";
}

.tablink {
    background-color: #555;
    color: white;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    font-size: 17px;
    width: 50%;
}

.tablink:hover {
    background-color: #777;
}

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */
```
Pero al ingresar al JavaScript no encontramos nada:
```JavaScript
function openTab(tabName,elmnt,color) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tabcontent");
    for (i = 0; i < tabcontent.length; i++) {
	tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tablink");
    for (i = 0; i < tablinks.length; i++) {
	tablinks[i].style.backgroundColor = "";
    }
    document.getElementById(tabName).style.display = "block";
    if(elmnt.style != null) {
	elmnt.style.backgroundColor = color;
    }
}

window.onload = function() {
    openTab('tabintro', this, '#222');
}

/* How can I keep Google from indexing my website? */
```
Recordemos que robots nos permite dejar que indexen o no nuestra página
```
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```
Aquí nos da una pequeña pista con el access, pues hay una página en apache de acceso, la cual es .htaccess, al entrar aquí encontramos lo siguiente:
```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```
Ahora, al desarrollar en mac se crea una carpeta llamada .DS_Store, a la cual entramos también:
```
Congrats! You've completed the scavenger hunt! Part 5: _9588550}
```

---
# Flag del reto
>picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}

---
# Notas adicionales

---
# Referencias

Pistas de [apache](https://chatgpt.com/share/699f9c1b-a908-800b-a79a-983487e00103).
Pistas de [mac](https://chatgpt.com/share/699f9d91-2be0-800b-8568-00e75cfb595e).