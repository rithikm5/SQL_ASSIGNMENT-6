# SQL_ASSIGNMENT-6
# Create a table for students which should contain the following columns id, name, subject,mark,course.

CREATE TABLE Students (
    ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Subject VARCHAR(50),
    Mark INT,
    Course VARCHAR(50)
);

INSERT INTO Students VALUES
(1, 'Rithik', 'Maths', 99, 'B.Sc'),
(2, 'Priya', 'Science', 72, 'B.Sc'),
(3, 'Ravi', 'English', 90, 'B.A'),
(4, 'Divya', 'Maths', 65, 'B.Sc'),
(5, 'Karthik', 'Science', 78, 'B.Tech'),
(6, 'Meena', 'English', 95, 'B.A');

#  Write subquery which should return student details whose mark should be grater than average.
SELECT *
FROM Students
WHERE Mark >
(
    SELECT AVG(Mark)
    FROM Students
);

# Write a multi row subquery which should contain students with marks > 50
SELECT *
FROM Students
WHERE ID IN
(
    SELECT ID
    FROM Students
    WHERE Mark > 50
);
