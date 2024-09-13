ESERCIZI CON GROUP BY
<!-------------------------------------------------------->
1- Contare quanti iscritti ci sono stati ogni anno
soluzione
SELECT YEAR(`enrolment_date`) AS `anno`, COUNT(*) AS `iscritti`
FROM `students`
GROUP BY YEAR(`enrolment_date`);