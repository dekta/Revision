### Sql general queries:

#### select data base
    USE db_name

#### Show Databases
    SHOW DATABASES;

#### Create Database
    CREATE DATABASE db_name;

#### Work on a database
    USE db_name;

#### Show Tables
    CREATE TABLE students (name varchar(255),email varchar(50),batch varchar(20));

#### Table Information
    DESCRIBE students;


#### Delete Table
    DROP TABLE students;


#### Reset Table Data
    TRUNCATE TABLE students;

#### Delete Database
    DROP DATABASE db_name;


#### Create Data
    INSERT INTO students ( name, email, batch)VALUES ("e", "e@gmail.com", "xyz");


#### Read Data
    SELECT * FROM students;SELECT name FROM students where name = 'e';


#### Update Data
    UPDATE students SET batch = "Cohort-1" where name = 'e';


#### Delete Data
    DELETE FROM students;
    DELETE FROM students where name = 'e';


### WHERE CLAUSE
- Get all the users 
    SELECT * FROM user_data;

- Get all the users where gender is Male 
    SELECT * FROM user_data WHERE gender = "Male";

- Get all the users where gender is not Male 
    SELECT * FROM user_data WHERE NOT gender = "Male";
    SELECT * FROM user_data WHERE gender != "Male";

-  Get all the users where gender is Male and language is Hindi 
    SELECT * FROM user_data WHERE gender = "Male" and language = "Hindi";

- Get all the users where gender is Male and language is not Hindi 
    SELECT * FROM user_data WHERE gender = "Male" and NOT language = "Hindi";
    SELECT * FROM user_data WHERE gender = "Male" and language != "Hindi";

- Get all the users where shirt size is L or XL 
    SELECT * FROM user_data WHERE shirt_size = "L" or shirt_size = "XL";
    SELECT * FROM user_data WHERE shirt_size IN ("L", "XL");

- Combining multiple conditions 
    SELECT * FROM user_data WHERE (gender = "Male" and shirt_size = 'L') OR (gender = "Female" and shirt_size = 'M');
    SELECT * FROM user_data WHERE ((gender = "Male" and shirt_size = 'L') OR (gender = "Female" and shirt_size = 'M')) AND language = "English";
    SELECT * FROM user_data WHERE ((gender = "Male" and shirt_size = 'L') OR (gender = "Female" and shirt_size = 'M')) AND language IN ("English", "Hindi");




