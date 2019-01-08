#Query01
´´´
CREATE DATABASE call_list;


\c call_list


CREATE TABLE users (id SERIAL PRIMARY KEY, first_name VARCHAR(15), email VARCHAR(40));

INSERT INTO users (id, first_name, email) values (1, 'Carlos', 'Carlos@gmail.com');


INSERT INTO users (id, first_name, email) values (2, 'Laura', 'Laura@gmail.com');

CREATE TABLE calls (id SERIAL PRIMARY KEY, phone INTEGER, calls_date DATE, user_id INTEGER);


ALTER TABLE USERS ADD COLUMN last_name VARCHAR(15);

UPDATE users SET last_name = 'Herrera' WHERE first_name = 'Carlos';


UPDATE users SET last_name = 'Garcia' WHERE first_name = 'Laura';


INSERT INTO calls (id, phone, calls_date, user_id)
    VALUES (1, 99117403,'10-12-18', 1);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (2, 99117404,'11-12-18', 1);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (3, 99117404,'12-12-18', 1);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (4, 99117404,'12-13-18', 1);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (5, 81327036,'12-14-18', 1);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (6, 991555333,'12-15-18', 1);


llamadas de Carlos

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (7, 98765432,'12-10-18', 2);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (8, 98765432,'12-11-18', 2);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (9, 98765432,'12-12-18', 2);

INSERT INTO calls (id, phone, calls_date, user_id)
VALUES (10, 98765432,'12-12-18', 2);


INSERT INTO users (id, first_name, email, last_name) values (3, 'Malcolm', 'Malcolm@gmail.com', 'Lenn');


SELECT first_name, count(*) FROM users, calls WHERE calls.user_id = users.id group by first_name;


SELECT * FROM calls WHERE calls.user_id = 2 ORDER BY calls_date DESC;

