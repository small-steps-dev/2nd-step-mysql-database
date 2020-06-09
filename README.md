# 2nd-step-mysql-database

https://cloud.google.com/sql/docs/mysql/quickstart
https://www.javatpoint.com/mysql-tutorial

gcloud sql connect mysql-db --user=root

CREATE DATABASE 1st_step;
SHOW DATABASES;

CREATE USER 'mysql_db_admin'@'%' IDENTIFIED BY '[PASSWORD]';
CREATE USER 'mysql_db_user'@'%' IDENTIFIED BY '[PASSWORD]';
SELECT user, host FROM mysql.user;

GRANT ALL PRIVILEGES ON 1st_step.* TO 'mysql_db_admin'@'%';
GRANT SELECT, INSERT, UPDATE, DELETE ON 1st_step.* TO 'mysql_db_user'@'%';
FLUSH PRIVILEGES;
SHOW GRANTS FOR mysql_db_user;  


gcloud sql connect mysql-db --user=mysql_db_admin

USE 1st_step;
CREATE TABLE notes(
   id INT NOT NULL AUTO_INCREMENT,
   text TEXT NOT NULL,
   PRIMARY KEY (id)
);
SHOW TABLES;


gcloud sql connect mysql-db --user=mysql_db_user

SELECT * FROM notes;
INSERT INTO notes (text) VALUES ("test");
SELECT * FROM notes;
DELETE FROM notes;
SELECT * FROM notes;
INSERT INTO notes (text) VALUES ("test");
SELECT * FROM notes;
