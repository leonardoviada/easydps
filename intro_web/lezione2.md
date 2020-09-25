# Lezione 2

## Styling CSS

Una volta definito lo "scheletro" della nostra pagina web - vedi lez. precedente - ci renderemo conto di quanto sia triste e poco personalizzata. Ad esempio il carattere è quello di default, idem per colori e layout.
Corre in nostro soccorso il CSS, il Cascading Style Sheet: **un linguaggio per fogli di stile utilizzato per descrivere la presentazione di un documento** scritto in HTML o XML (inclusi vari linguaggi XML quali SVG o XHTML). Il CSS descrive come gli elementi dovrebbero apparire sui diversi tipi di dispositivo e mezzo.

E' uno dei linguaggi fondamentali dell'open Web ed è standardizzato nei browser web secondo la [specifica W3C](https://www.w3.org/standards/#:~:text=W3C%20standards%20define%20an%20Open,are%20available%20on%20any%20device).

### Sintassi: Proprietà

La stesura del codice CSS viene implementata mediante la configurazione di determinate proprietà - [vedi reference](#reference-css) - e relativi valori.
Le componenti di base di un blocco di codice CSS sono meglio riportate nell'esempio che segue.

?> I commenti in CSS seguono la seguente sintassi: `/* contenuto commnento */`

```css
selettore {
  proprietà: valore;
}
```

### Collegamento al DOM

Possiamo applicare il nostro "styling" in 3 principali modalità.

- #### Inline

  L'opzione più semplice e immediata, consiste nel riportare le proprietà del CSS - **quindi NO selettore nè parentesi graffe** - direttamente all'interno del particolare attributo `style` di un tag HTML.

  ```html
  <h1 style="color:red;font-weight:500;font-style:italic">Sono Stiloso</h1>
  ```

- #### Head

  Vede i nostri blocchi di stile nel tag `<head>` del documento che stiamo redigendo. La sintassi **comprende selettori e parentesi graffe**.

  ```html
  <head>
    [...]
    <style>
      h1 {
        color: red;
        font-weight: 500;
        font-style: italic;
      }
    </style>
    [...]
  </head>
  <body>
    [...]
    <h1>Sono Stiloso, pt.2</h1>
    [...]
  </body>
  ```

- #### Esterno

  Il metodo più strutturato e "scalabile". Prevede l'utilizzo di un foglio di stile esterno - quindi un documento `.css` di cui riporteremo percorso e nome - all'interno del quale lavorare alle nostre proprietà.

  _style.css_

  ```css
  h1 {
    color: red;
    font-weight: 500;
    font-style: italic;
  }
  ```

  _index.html_

  ```html
  <head>
    [...]
    <link rel="stylesheet" href="%PERCORSO%/style.css" />
    [...]
  </head>
  <body>
    [...]
    <h1>Sono Stiloso, pt.3</h1>
    [...]
  </body>
  ```

  ?> **L'attributo `rel` indica il tipo di relazione fra una risorsa collegata e il documento in oggetto.** Tutte le sue opzioni e caratteristiche sono riportate esaustivamente nell'[apposita pagina MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel).
  In contesti simili si possono incontrare anche gli attributi `type` e `media`. Il primo viene utilizzato semplicemente per descrivere il tipo della risorsa in collegamento, il secondo per associare una risorsa a un dato tipo di dispositivo - E.G. Fogli di stile differenti per mobile e desktop. [Approfondisci qui](https://www.w3schools.com/tags/att_link_media.asp)

---

### Reference CSS

**[Link alla reference CSS 🔗](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)**

Le proprietà e i relativi valori del CSS sono innumerevoli. Alcune saranno coperte nelle lezioni successive, mentre la lista completa è accessibile online da diverse fonti. <br>
Il Mozzilla Developer Network offre una completa raccolta di tutte le proprietà CSS con nozioni teoriche, dettagli, approfondimenti e riferimenti pratici.<br>
MDN può aiutarci anche con diverse altre tecnologie web lato client.
