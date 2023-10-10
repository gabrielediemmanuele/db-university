## SQL TASK - Esercizio di gruppo pomeridiano

> Ecco un esempio di una possibile struttura per un database di una biblioteca utilizzando MySQL:

- Tabella "libri":
  id (chiave primaria, intero)
  titolo (varchar)
  autore_id (intero, chiave esterna alla tabella "autori")
  genere_id (intero, chiave esterna alla tabella "generi")
  numero_copie (intero)

- Tabella "autori":
  id (chiave primaria, intero)
  nome (varchar)

- Tabella "generi":
  id (chiave primaria, intero)
  nome (varchar)

- Tabella "utenti":
  id (chiave primaria, intero)
  nome (varchar)
  indirizzo (varchar)
  data_registrazione (data)

- Tabella "prestiti":
  id (chiave primaria, intero)
  libro_id (intero, chiave esterna alla tabella "libri")
  utente_id (intero, chiave esterna alla tabella "utenti")
  data_prestito (data)
  data_restituzione (data)

```sql
--
```

<hr>
