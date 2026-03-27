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
eg. SELECT FIRST_NAME,SALARY FROM WORKER;


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


11. for Deleting table data
TRUNCATE TABLE table_name;
eg. TRUNCATE TABLE CUSTOMER;


12.for drop(delete) table
DROP TABLE IF EXISTS table_name;
eg. DROP TABLE IF EXISTS WORKER;


13. for drop(delete) column
ALTER TABLE table_name DROP COLUMN  col_name;
eg. ALTER TABLE ACCOUNT DROP COLUMN SAVING_INTERSET;


14.for rename table
ALTER TABLE old_table_name RENAME TO new_table_name;
eg. ALTER TABLE ACCOUNT RENAME TO ACCOUNT_DETAILS;


15.for update data on column
eg. UPDATE CUSTOMER SET ADDRESS='MUMBAI',GENDER='M' WHERE ID=121;
eg. UPDATE CUSTOMER SET PINCODE=1100000;


16.use where
eg. SELECT * FROM WORKER WHERE SALARY>100000;
eg. DELETE FROM CUSTOMER WHERE ID=1;


17.use between(use AND)
 -- salary [80000,300000]
eg.   SELECT * FROM WORKER WHERE SALARY BETWEEN 80000 AND 300000;


18.use IN
eg. SELECT * FROM WORKER WHERE DEPARTMENT IN ('HR','Admin','Account');


19.use OR
eg. SELECT * FROM WORKER WHERE DEPARTMENT='HR' OR DEPARTMENT='Admin';


20.use NOT
eg. SELECT * FROM WORKER WHERE DEPARTMENT NOT IN('HR','Admin');


21.use IS NULL
eg. SELECT * FROM WORKER WHERE PIN_CODE IS NULL;


22.use wildcard
eg. SELECT * FROM WORKER WHERE FIRST_NAME LIKE '_p%';


23.order by ascending
eg. SELECT * FROM WORKER ORDER BY SALARY ASC;


24.order by descending
eg. SELECT * FROM WORKER ORDER BY SALARY DESC;


25.group by
eg. SELECT DEPARTMENT FROM WORKER GROUP BY DEPARTMENT;


26.group by(count)
eg. SELECT DEPARTMENT,COUNT(DEPARTMENT) FROM WORKER GROUP BY DEPARTMENT;


27.group by(sum)
eg. SELECT DEPARTMENT,SUM(SALARY) FROM WORKER GROUP BY DEPARTMENT;


28.group by(AVG)
eg. SELECT DEPARTMENT,AVG(SALARY) FROM WORKER GROUP BY DEPARTMENT;


29.group by(min)
eg. SELECT DEPARTMENT,MIN(SALARY) FROM WORKER GROUP BY DEPARTMENT;


30.group by(max)
eg. SELECT DEPARTMENT,MAX(SALARY) FROM WORKER GROUP BY DEPARTMENT;


31.distinct
eg. SELECT DISTINCT DEPARTMENT FROM WORKER;


32.group by having
eg. SELECT DEPARTMENT,COUNT(DEPARTMENT) FROM WORKER GROUP BY DEPARTMENT HAVING COUNT(DEPARTMENT)>2  ;


33.check
eg.   CREATE TABLE CUSTOMER(
         age INT,
         CONSTRAINT age_check CHECK(age>12);
      )



34. change column
   ALTER TABLE table_name CHANGE COLUMN old_col_name new_col_name VARCHAR(1024);
   eg. ALTER TABLE CUSTOMER CHANGE COLUMN NAME CUSTOMER_NAME VARCHAR(1024);




35.












