Università = 
Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.


- departments
- courses
- teachers
- appeals_exame
- students
- appeals_vote



Table = departments
- id    | INDEX | INT or BIGINT | NOTNULL | UNIQUE | AI 
- name  | VARCHAR(50) | NN |





Table = courses
- id    | INDEX | INT or BIGINT | NOTNULL | UNIQUE | AI 
- departments_id (FK)
- faculty | VARCHAR(50) | NN |
- course  | VARCHAR(50) | NN |
- date    | DATE | NN |
- teachers_id   (FK)
- note    | TEXT | NULL | 





Table = teachers
- id    | INDEX | INT or BIGINT | NOTNULL | UNIQUE | AI 
- full_name | VARCHAR(30) | NN |
- email | VARCHAR(100) | NN |
- date   | DATE | NN |
- image | VARCHAR(255) | NULL | DEFAULT('https/images')
- note  | TEXT | NULL | 






Table = appeals_exame
- id    | INDEX | INT or BIGINT | NOTNULL | UNIQUE | AI 
- corses_id     (FK)
- teacher_id
- date  | DATE | NN |





Table = students
- id    | INDEX | INT or BIGINT | NOTNULL | UNIQUE | AI 
- full_name   | VARCHAR(30) | NN |
- date   | DATE | NN |
- image  | VARCHAR(255) | NULL | DEFAULT('https/images')
- email  | VARCHAR(100) | NN |   
- number_student | INI | NN |   






Table = appeals_vote
- id    | INDEX | INT or BIGINT | NOTNULL | UNIQUE | AI 
- students_id (FK)
- appeals_exame (FK)
- appeal_vote | TINYINT | NULL | DEFAULT('in approvazione')








