1.for creating database
CREATE DATABASE database_name;
eg. CREATE DATABASE ORG;


2.for show database
SHOW DATABASES;


3. for use database
USE database_name;
eg. USE ORG;


4.for creating table
CREATE TABLE table_name(
     all attribute with data type present here
)
eg. CREATE TABLE CUSTOMER(
          ID INTEGER PRIMARY KEY,
          CNAME VARCHAR(255),
          ADDRESS VARCHAR(255),
          GENDER VARCHAR(255),
          CITY VARCHAR(255),
          PINCODE INTEGER
    );


4.for insert the data
INSERT INTO table_name
        (all attribute) VALUES
                           (1st row all data),
                           (2nd row all data);
eg. INSERT INTO CUSTOMER
        (ID,CNAME,ADDRESS,GENDER,CITY,PINCODE) VALUES
              (1251,'RAM KUMAR','DILBAGH NAGAR','M','JALANDHAR',144002),
              (1300,'SHAYAM SINGN','LUDHIANA H.O','M','LUDHIANA',141001),
              (245,'NEELABH SHUKLA','ASHOK NAGAR','M','JALANDHAR',144003),
              (210,'BARKHA SINGH','DILBAGH NAGAR','F','JALANDHAR',144002),
              (500,'ROHAN ARORA','LUDHIANA H.O','M','LUDHIANA',141001); 


5. for insert the data
INSERT INTO table_name VALUES(all data);
eg. INSERT INTO CUSTOMER VALUES(121,'BOB');


6.for show the data with table
SELECT * FROM table_name;
eg. SELECT * FROM CUSTOMER;


7. for access any secure data
 SET SQL_SAFE_UPDATES = 0;
 SET SQL_SAFE_UPDATES = 1;


 8.for describe the table
 DESC table_name;
 eg. DESC CUSTOMER;


9.add new column
ALTER TABLE table_name ADD col_name data_type ;
eg. ALTER TABLE ACCOUNT ADD INTEREST FLOAT NOT NULL DEFAULT 0;


10.modify column
ALTER TABLE table_name MODIFY col_name data_type ;
ALTER TABLE ACCOUNT MODIFY INTEREST DOUBLE NOT NULL DEFAULT 0;




