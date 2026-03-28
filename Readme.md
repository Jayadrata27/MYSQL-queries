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




35.Replace table_data
REPLACE INTO table_name SET col1=val1,col2=val2;
eg. REPLACE INTO CUSTOMER SET ID=1300,CNAME='MAC',CITY='UTAH';
eg. REPLACE INTO CUSTOMER(ID,CNAME,CITY) VALUES(1233,'CODEHELP','COLONY');




36.inner join
SELECT C.* ,O.* FROM CUSTOMER AS C 
   INNER JOIN ORDER AS O ON C.ID=O.CUSTID;

   Enlist all the employees ID's, names along with the Project allocated to them.
eg. SELECT E.ID,E.FNAME,E.LNAME,P.ID,P.NAME FROM EMPLOYEE AS E 
       INNER JOIN PROJECT AS P ON E.ID=P.EMPID;

eg. SELECT E.ID,E.FNAME,E.LNAME,P.ID,P.NAME FROM EMPLOYEE AS E, PROJECT AS P WHERE E.ID=P.EMPID;  

Enlist all the element on of the tables
eg. SELECT * FROM EMPLOYEE AS E 
       INNER JOIN PROJECT AS P ON E.ID=P.EMPID;



37.left join
SELECT C.* ,O.* FROM CUSTOMER AS C 
   LEFT JOIN ORDER AS O ON C.ID=O.CUSTID;
eg. SELECT * FROM EMPLOYEE AS E
    LEFT JOIN PROJECT AS P ON E.ID=P.EMPID;


38.right join
SELECT C.* ,O.* FROM CUSTOMER AS C 
   RIGHT JOIN ORDER AS O ON C.ID=O.CUSTID;
eg. SELECT E.FNAME,E.LNAME,E.EMAILID,P.ID,P.NAME FROM EMPLOYEE AS E
    RIGHT JOIN PROJECT AS P ON E.ID=P.EMPID;


39.cross join
eg. SELECT E.FNAME,E.LNAME,P.ID,P.NAME FROM EMPLOYEE AS E
     CROSS JOIN PROJECT AS P;



40.union
eg.     SELECT * FROM DEPT1
        UNION
        SELECT * FROM DEPT2;


41.intersection
        list out all the employees who work in all the departments
        eg.  SELECT DEPT1.* FROM DEPT1
              INNER JOIN DEPT2 USING(EMPID);


42.minus
      List out all the employees working in dept1 but not in dept2.
      eg.   SELECT * FROM DEPT1
            LEFT JOIN DEPT2 USING(EMPID)
            WHERE DEPT2.EMPID IS NULL;



43. SUB QUERIES
    -- WHERE clause same table
    -- employees with age > 30
    SELECT * FROM EMPLOYEE WHERE AGE IN(SELECT AGE FROM EMPLOYEE WHERE AGE>30);



     -- WHERE clause different table
     -- emp details working in more than 1 project.
     SELECT * FROM EMPLOYEE WHERE ID IN(SELECT EMPID FROM PROJECT GROUP BY EMPID HAVING COUNT(EMPID)>1);



     -- single value subquery
     -- emp details having age> avg(age)
     SELECT * FROM EMPLOYEE WHERE AGE>(SELECT AVG(AGE) FROM EMPLOYEE);



     -- FROM clause derived tables
     -- select max age person whose first name contains 'a'
     SELECT MAX(AGE) FROM (SELECT * FROM EMPLOYEE WHERE FNAME LIKE '%a%') AS COMPANY;



    -- Corelated subquery
    -- find 3rd oldest employee
    SELECT *
    FROM EMPLOYEE AS E1
    WHERE 3=(
        SELECT COUNT(E2.AGE)
        FROM EMPLOYEE AS E2
        WHERE E2.AGE>=E1.AGE
       );





 44.view
    -- CREATING A VIEW
    CREATE VIEW CUSTOM_VIEW AS SELECT FNAME,AGE FROM EMPLOYEE;


    -- viewing  from view
    SELECT * FROM CUSTOM_VIEW;    


    -- alter the view
    ALTER VIEW CUSTOM_VIEW AS SELECT FNAME,LNAME,AGE FROM EMPLOYEE; 


    -- droping the view
    DROP VIEW IF EXISTS CUSTOM_VIEW;










