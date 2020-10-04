# Lezione 2.1

## Selettori

Come lavorare con specifici elementi all'interno della pagina? Utilizziamo i selettori.

### Di Base

1. #### Selettore Universale

   Seleziona tutti gli elementi.

   ```css
   * {
     background-color: green;
   }
   ```

2. #### Selettore per Tipo

   Seleziona i tag specificati.

   ```css
   /* Seleziona tutti gli anchor tag */
   a {
     text-decoration: none;
   }

   /* Seleziona tutti gli heading */
   h1 {
     font-family: 'Poppins';
     font-weight: 500;
   }
   ```

3. #### Selettore per Classe

   Lavora sui tag con classe specificata. <br>
   Segue la sintassi `.nomeclasse`

   ```css
   .container {
     max-width: 1024px;
   }
   ```

   _tag selezionato_

   ```html
   <div class="container"></div>
   ```

4. #### Selettore per ID

   Individua uno specifico elemento collegato ad un ID - [⚠️che deve essere univoco](https://www.w3schools.com/html/html_id.asp#google_ads_iframe_/22152718/sws-hb//w3schools.com//main_leaderboard_0:~:text=You%20cannot%20have%20more%20than%20one%20element%20with%20the%20same%20id%20in%20an%20HTML%20document.). <br>
   Segue la sintassi `#id`

   ```css
   #wrappper {
     padding: 1rem;
     display: flex;
     justify-content: between;
   }
   ```

   _tag selezionato_

   ```html
   <div id="wrapper"></div>
   ```

5. #### Selettore per Attributo

   Seleziona elementi basandosi sulla presenza di un dato attributo e/o valore.

   ```css
   a[href="https://notes-info.netlify.app/#/"]
   {
     color: green;
   }
   ```

   _tag selezionato_

   ```html
   <!-- selezionato -->
   <a href="https://notes-info.netlify.app/#/">Clicca qui</a>

   <!-- non selezionato -->
   <a href="https://graffitis.itiscuneo.gov.it/">Clicca qui</a>
   ```

### Lista

Utilizza `, ` per selezionare nodi multpli.

```css
div,
span {
  border: red 2px solid;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: helvetica;
}
```

### Combinatori

1. #### Discendenza

   Tipicamente rappresentato da uno spazio (` `), ma considera validi anche i caratteri di carriage return, new line, tab e simili.<br>
   Seleziona nodi che "discendono" dal primo elemento. Combina due selettori in modo tale che gli elementi individuati dal secondo selettore siano selezionati **solo se tra i loro "antenati" è presente un elemento di match con il primo selettore**.

   ```css
   li {
     list-style-type: disc;
   }

   li li {
     list-style-type: circle;
   }
   ```

   _tag selezionati_

   ```html
   <ul>
     <li>
       <div>Item 1</div>
       <ul>
         <li>Subitem A</li>
         <li>Subitem B</li>
       </ul>
     </li>
     <li>
       <div>Item 2</div>
       <ul>
         <li>Subitem A</li>
         <li>Subitem B</li>
       </ul>
     </li>
   </ul>
   ```

2. #### Figli

   Più specifico rispetto al combinatore di discendenza, utilizza il separatore `>`, e seleziona soltanto gli elementi di match del secondo selettore **direttamente figli del primo**.

   ```css
   div > span {
     background-color: DodgerBlue;
   }
   ```

   _tag selezionato_

   ```html
   <div>
     <span>
       Span #1, nel div
       <span>Span #2, nello span dentro il div</span>
     </span>
   </div>
   <span>Span #3, fuori dal div</span>
   ```

3. #### Parente adiacente

   Fa uso del separatore `+` e seleziona il secondo elemento **solo se segue immediatamente il primo, e tutti e due hanno lo stesso nodo genitore**.

   ```css
   /* fa utilizzo di una pseudo classe, vedi sezione successiva */
   li:first-of-type + li {
     color: red;
   }
   ```

   _tag selezionato_

   ```html
   <ul>
     <li>One</li>
     <li>
       <!-- unico elemento selezionato -->
       Two!
     </li>
     <li>Three</li>
   </ul>
   ```

### Pseudo Classi

Una pseudo classe, in CSS, è una parola chiave aggiunta a un selettore che ne specifica un particolare stato. Mediante l'utilizzo di una pseudo classe è possibile applicare determinate regole di stile ad un elemento non solo in relazione a proprietà del documento, ma a fattori esterni. <br>
**E.G.** `:visited` per i tag anchor o `:hover` in relazione alla posizione del mouse.

```css
selettore:pseudo-classe {
  proprietà: valore;
}
```

---

### Reference Selettori CSS

**[Link alla reference 🔗](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)**

Sono riportate tipologie pià avanzate e complesse di selettori, cenni teorici e pratici.<br>
MDN può aiutarci anche con diverse altre tecnologie web lato client.
