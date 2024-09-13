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

3- Calcolare la media dei voti di ogni appello d'esame
soluzione
SELECT `exam_id`, AVG(vote) AS media_voti
FROM `exam_student`
GROUP BY `exam_id`;

ESERCIZI CON JOIN
<!----------------------------------------------------->
1- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
SOLUZIONE
SELECT `students`.id, `students`.name, `degrees`.id, `degrees`.name
FROM `students`
JOIN `degrees` ON `students`.degree_id = `degrees`.id
WHERE `degrees`.name = 'Corso di Laurea in Economia';

2- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
soluzione
SELECT `degrees`.id, `degrees`.name, `departments`.id AS `department_id`, `departments`.name AS `department_name`
FROM `degrees`
JOIN `departments` ON `degrees`.department_id = `departments`.id
WHERE `departments`.name = 'Neuroscienze' 
AND `degrees`.name = 'Magistrale';
(insieme vuoto non funziona da correggere)

3- Selezionare tutti i corsi in cui insegna Fulvio Amato
soluzione
SELECT `courses`.id, `courses`.`name`, `teachers`.name, `teachers`.`surname`
FROM `courses`
JOIN `course_teacher` ON `courses`.id = `course_teacher`.course_id
JOIN `teachers` ON `course_teacher`.teacher_id = `teachers`.id
 WHERE `teachers`.`name` LIKE '%Fulvio%';
