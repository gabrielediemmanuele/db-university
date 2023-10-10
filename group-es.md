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
-- Selezionare tutti i prestiti effettuati da un determinato utente.
SELECT (*)
FROM `prestiti`
WHERE `utente_id` = 2;
```

<hr>

```sql
--  Selezionare tutti i prestiti restituiti entro una data specifica.
SELECT (*)
FROM `prestiti`
/* WHERE `data_restituzione` = "data"; */
WHERE `data_restituzione` <= "2021-05-31";
```

<hr>

```sql
-- Selezionare tutti gli utenti che hanno preso in prestito
-- almeno un libro di un determinato genere
SELECT DISTINCT  `utenti`.`nome`, `generi`.`nome`
FROM `utentu`
JOIN `prestiti` ON `prestiti`.`utente_id` = `utenti`.`id`
JOIN `libri` ON `prestiti`.`libro_id` = `libri`.`id`
JOIN `generi` ON `libri`.`genere_id` = `generi`.`id`
WHERE 1

```

<hr>

```sql
-- contare quanti libri gli uten ti hanno preso in prestito nel 2021
-- raggruppati per genere.
SELECT COUNT(`libri`.`id`) AS "Numero", `generi`.`nome`
FROM `libri`
JOIN `generi` ON `libri`.`genere_id` = `generi`.`id`
JOIN `prestiti` ON `prestiti`.`libro_id` = `libri`.`id`

WHERE YEAR(`prestiti`.`data_prestito`) = 2021
GROUP BY  `generi`.`nome`;
```

<hr>
