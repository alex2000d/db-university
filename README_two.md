ESERCIZI CON GROUP BY
<!-------------------------------------------------------->
1- Contare quanti iscritti ci sono stati ogni anno
soluzione
SELECT YEAR(`enrolment_date`) AS `anno`, COUNT(*) AS `iscritti`
FROM `students`
GROUP BY YEAR(`enrolment_date`);

2- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
soluzione
SELECT COUNT(*) AS `numero_insegnanti`, `office_address`
FROM `teachers`
GROUP BY `office_address`;