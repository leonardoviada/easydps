# Esercizio 1

## CSS Layout

Riprodurre la disposizione in figura mediante [CSS Vanilla](https://stackoverflow.com/questions/40115768/what-is-vanilla-css-and-why), a partire dal codice HTML dato.

### Codice

_index.html_

```html
<!DOCTYPE html>
<html lang="it">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>layout_es1</title>
  </head>
  <body>
    <div class="contenitore">
      <div class="intestazione">Intestazione</div>
      <div class="contenuto">Contenuto</div>
      <div class="nav">Navbar</div>
      <div class="menu">
        <h2>Archivio</h2>
        <ul>
          <li>Lorem</li>
          <li>Ipsum</li>
          <li>Dolor</li>
        </ul>
      </div>
      <div class="footer">Footer</div>
    </div>
  </body>
</html>
```

_app.css_

```css
body {
  margin: 0px;
  padding: 0px;
  font-size: 85%;
  font-family: Verdana, sans-serif;
  text-align: center;
  color: black;
  background-color: white;
}

#contenitore {
  padding: 0px;
  margin: 1em auto;
  position: relative;
  width: 630px;
  height: 150px; /* per vederlo... */
  text-align: left;
  background-color: lightgrey;
  border: 1px solid black;
}

#intestazione {
  height: 80px;
  background-color: red;
}

#contenuto {
  margin-top: 25px;
  margin-left: 129px;
  background-color: yellow;
}

#nav {
  position: absolute;
  top: 80px;
  left: 0px;
  height: 25px;
  width: 100%;
  background-color: lightgreen;
  border-top: solid white 1px;
  padding-top: 5px;
  background-color: #ffdf71;
}

#nav a {
  padding-left: 0.7em;
  padding-right: 1em;
  border-right: white solid 1px;
}

#menu {
  position: absolute;
  top: 115px;
  left: 0px;
  width: 109px;
  background-color: cyan;
  padding-top: 25px;
  border-left: solid 1px #ffdf71;
}

#footer {
  height: 20px;
  background-color: #ffdf71;
  border-bottom: solid white 1px;
  text-align: right;
  font-size: 75%;
  padding-top: 0.4em;
  padding-right: 1em;
}

.corsivo {
  font-style: italic;
}

h1 {
  font-family: serif;
  color: red;
  font-size: 1.8em;
  font-weight: normal;
}

h2 {
  font-family: serif;
  color: red;
  font-size: 1.5em;
  font-weight: normal;
}

h3 {
  margin-top: -1.1em;
  font-family: serif;
  color: #ff6666;
  font-size: 1.3em;
  font-weight: normal;
  font-style: italic;
}

ul {
  padding: 0px;
  margin-left: 1.5em;
}
```
