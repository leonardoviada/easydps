# Lezione 1

## HTML e CSS

### I Tag

Le entità che definiscono la struttura della pagina, consentendo ad altre tecnologie lato client (CSS, JavaScript) di interagirvi contribuendo alla realizzazione dell'interfaccia presentata all'utente.
Tutte le informazioni necessarie a queste interazioni sono contenute all'interno di **attributi**, composti da chiave e valore. <br>
I tag possono permettere l'inserimento di contenuto al loro interno, o rappresentare uno specifico elemento che non possiede entità annidate - detto **Self Closing Tag**.

?> In quanto utilizzati nel codice sottostante, la sintassi dei commenti è
`<!-- contenutoCommento -->`

```html
<tag chiaveAttr="valoreAttr">contenuto</tag> <br />
<!-- 
  Il tag <br/> è utilizzato per forzare il ritorno 
  a capo, è un esempio di Self Closing Tag
-->
<selfClosingTag chiaveAttr="valoreAttr" />
```

Vengono inseriti all'interno di un documento con estensione `.html` e richiedono una specifica struttura (boilerplate).

```html
<!DOCTYPE html>
<!-- Definizione del tipo documento -->

<html lang="it">
  <!-- Il tag "init", che contiene tutti gli altri tag del foglio -->

  <head>
    <!-- 
      Contiene informazioni non visibili nell'iterfaccia.
      Utilizzato per collegamenti a contenuti esterni e, ad esempio, 
      dati su autore e parole chiave a fini SEO (vedi glossario) 
    -->

    <meta charset="UTF-8" />
    <!-- Definisce il character encoding del documento -->

    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- Comunica al browser i parametri per gestire
     le dimensioni della pagina e relativa scala -->

    <title>La mia Pagina HTML</title>
    <!-- Titolo visualizzato nella tab del browser e utilizzato (in parte) dai motori di ricerca. -->
  </head>
  <body>
    <!-- Tutto il contenuto visibile della pagina è chiuso qui -->
  </body>
</html>
```
