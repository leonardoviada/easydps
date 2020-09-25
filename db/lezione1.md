# Lezione 1

## Tiplogie di Database

### Gerarchici

| **Struttura** | Albero 🌳                    |
| ------------- | ---------------------------- |
| **Esempi**    | IBM DL/1 (Con IMD come DBMS) |

### Reticolari

| **Struttura** | Grafo ❇️ |
| ------------- | -------- |
| **Esempi**    | Supra    |

### Relazionali

| **Struttura** | Vedi [diagrammi ER](https://users.dimi.uniud.it/~massimo.franceschet/teatro-sql/diagrammaER.html) |
| ------------- | ------------------------------------------------------------------------------------------------- |
| **Esempi**    | DB2, OracleDB, MySQL (MariaDB), SQLServer, PostGRES, SQLite                                       |

_Caratteristiche_ Utilizzano [SQL](#sql), le colonne hanno dei [tipi](#tipi-colonne)

_Esempio Dati_

```csv
id, nome
1, verdi
2, bianchi
3, rossi
```

### Ad Oggetti

| **Struttura** | Può presentarne una qualsiasi delle precedenti |
| ------------- | ---------------------------------------------- |
| **Esempi**    | ZODB                                           |

_Caratteristiche_
Non utilizzano i record, ma gli ogetti, che vengono convertiti grazie ad un [ORM](https://it.wikipedia.org/wiki/Object-relational_mapping#:~:text=In%20informatica%20l'Object%2DRelational,agli%20oggetti%20con%20sistemi%20RDBMS.)

### Documentali

| **Struttura** | Record a composizione variabile |
| ------------- | ------------------------------- |
| **Esempi**    | MongoDB                         |

_Caratteristiche_
Ogni record può presentare campi non in comune con gli altri

_Esempio Dati_

```json
  /* doc1 */
  "Viada": {
    "v1": 3
    "v2": 4
    "v3": 2
    "v4": 6
  }

  /* doc2 */
  "Rossi": {
    "v1": 10
    "v2": 6
    "media": 8
  }
```

## SQL

### Comandi

- Query: `SELECT`
- non-Query: `CREATE`, `UPDATE`, `DROP`, `INSERT`, `ALTER`

### Tipi Colonne

- Primitivi: `INTEGER/NUMERIC`, `REAL`, `VARCHAR`
- non-Primitivi: `BLOB`, `TIMESTAMP`, `IMAGE`, `DATE`

## Comunicazioni tra Client e Server nel contesto Database

Esempio di uso di un DB relazionale all'interno di un programma client

```c
char* risultato = mySQL_execute_query("SELECT pagamenti
FROM Studenti
WHERE nome_studente = 'Viada'");
printf("soldi ricevuti: %s\n", risultato);

int rc = mySQL_non_query(
"INSERT INTO Studenti
VALUES (3, "Viada", 10000);");
if (rc == 0) printf("tutto bene!"); else return -1;
```

!> Per evitare problemi durante la migrazione dei dati (da un DBMS ad un altro) conviene evitare di utilizzare tipi di dato non primitivi. <br>
Questo comporta la scrittura di frammenti di codice per il parsing delle colonne del DB che contengono dati non primitivi. <br>
**E.G.** Per salvare un Array possiamo utilizzare una stringa con un apposito protocollo definito per il parsing - `"item1##item2##item3"`, avremo bisogno quindi una funzione che ci consenta di riportare nel formato desiderato i dati - `mioArray = fieldArray.split('##')`

---

## Glossario Lezione

?>
_DBMS - Data Base Management System:_ Programma server che gestisce il DB<br>
_ODBC:_ API standard per accedere a un DBMS relazionale<br>
_JDBC:_ ODBC per Java<br>
_ADO:_ una API in .net per lavorare ad oggetti con un DBMS relazionale<br>
