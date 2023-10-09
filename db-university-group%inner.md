# DB University (Group & Inner Join)

_db-university_

![image](./university.png)

## Group

1. Contare quanti iscritti ci sono stati ogni anno.
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio.
3. Calcolare la media dei voti di ogni appello d'esame.
4. Contare quanti corsi di laurea ci sono per ogni dipartimento.

```sql
-- 1. Contare quanti iscritti ci sono stati ogni anno.
SELECT YEAR(`enrolment_date`), COUNT(*)
FROM `students`
GROUP BY YEAR(`enrolment_date`);
```

```sql
-- Seleziona l'anno di enrolment_date e **conta** tutto
SELECT YEAR(`enrolment_date`), COUNT(*)
-- dalla tabella studenti...
FROM `students`
-- raggruppando per l'anno di arruolamento.
GROUP BY YEAR(`enrolment_date`);
```

<hr>

```sql
-- 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio.
SELECT `office_address` AS `office_name`, COUNT(*)
FROM `teachers`
GROUP BY `office_address`;
```

```sql
-- Seleziona tutti gli indirizzi di ufficio e dai il nome d'ufficio, poi contali tutti
SELECT `office_address` AS `office_name`, COUNT(*)
-- dall'interno della tabella teachers
FROM `teachers`
-- e raggrupparli per indirizzi di ufficio di appartenenza.
GROUP BY `office_address`;
```

<hr>

```sql
-- 3. Calcolare la media dei voti di ogni appello d'esame.
SELECT  `exam_id` "appello_esame", AVG(`vote`) "media_voti"
FROM `exam_student`
GROUP BY `exam_id`;
```

<hr>
