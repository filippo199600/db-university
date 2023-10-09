# EX QUERY SELECT

### QUERYES:

1. Selezionare tutti gli studenti nati nel 1990 (160)

```sql
SELECT * FROM `students` WHERE `date_of_birth` LIKE '1990-%'
```

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

```sql
SELECT * FROM `courses` WHERE `cfu` > 10
```

3. Selezionare tutti gli studenti che hanno più di 30 anni

```sql
SELECT * FROM `students` WHERE `date_of_birth` <= '1993-10-06'
```

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)

```sql
SELECT * FROM `courses` WHERE `year` = '1' AND `period` = 'I semestre'
```

5.  Selezionare tutti gli appelli d esame che avvengono nel pomeriggio (dopo le 14) del
    20/06/2020 (21)

```sql
 SELECT * FROM `exams` WHERE `date` = '2020-06-20' AND `hour` > '14:00:00'
```

6. Selezionare tutti i corsi di laurea magistrale (38)

```sql

SELECT * FROM `degrees` WHERE `name` LIKE 'corso di laurea magistrale%'
```

7. Da quanti dipartimenti è composta l università? (12)

```sql
SELECT COUNT(*) FROM `departments`
```

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

```sql
SELECT COUNT(*) FROM `teachers` WHERE `phone` IS NULL
```

### QUERIES GROUP BY

1. Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT YEAR(`enrolment_date`) "anno_iscrizione", COUNT(*) "numero_studenti" FROM `students` GROUP BY YEAR(`enrolment_date`);
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT `office_address` "indirizzo_ufficio", COUNT(*) "numero_insegnanti" FROM `teachers` GROUP BY `office_address`;
```
