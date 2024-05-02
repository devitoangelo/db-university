## Group by

1. Contare quanti iscritti ci sono stati ogni anno
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
3. Calcolare la media dei voti di ogni appello d'esame
4. Contare quanti corsi di laurea ci sono per ogni dipartimento





1. Contare quanti iscritti ci sono stati ogni anno

SELECT DISTINCT YEAR(`enrolment_date`)  as anno ,COUNT(*) 
FROM `students`
GROUP BY `enrolment_date`;
(ho provato ha non far ripetere gli anni con DISTINCT ma non è ancora perfetto)


2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT COUNT(*)`office_address`
FROM teachers
GROUP BY `office_address`;


3. Calcolare la media dei voti di ogni appello d'esame
SELECT `exam_id`, AVG(`vote`) as MediaVoti
FROM `exam_student`
GROUP BY `exam_id`;


4. Contare quanti corsi di laurea ci sono per ogni dipartimento
SELECT `department_id`, COUNT(*)
FROM `degrees`
GROUP BY `department_id`;