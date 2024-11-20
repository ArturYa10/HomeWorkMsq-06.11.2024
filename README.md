use uni;

SELECT title 
FROM Competencies 
WHERE id NOT IN (
    SELECT competencies_id 
    FROM Teachers2Competencies
);



SELECT c.title AS course_title, s.name AS headman_name
FROM courses c
JOIN students s ON c.headman_id = s.id;


SELECT DISTINCT 
    st.name AS student_name, 
    headman.name AS headman_name
FROM students st
JOIN students2courses sc ON st.id = sc.student_id
JOIN courses c ON sc.course_id = c.id
JOIN students headman ON c.headman_id = headman.id;
