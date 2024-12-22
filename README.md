# Employee Database SQL

## Description
This SQL script defines and manages an employee database with the following functionalities:

- Creation of an `EMP` table to store employee details such as employee number, name, salary, commission, job title, hire date, and department number.
- Insertion of sample records into the `EMP` table.
- Retrieval and analysis of employee data through various SQL queries.

## Table Structure
```sql
CREATE TABLE EMP (
  ENO integer,
  ENAME text,
  SAL integer,
  COMM integer,
  JOB text,
  HIEREDATE text,
  DEPTNO integer 
);
```

## Sample Data
```sql
INSERT INTO EMP VALUES(1,'SMITH',800,150,'CLERK','10-DEC-80',10);
INSERT INTO EMP VALUES(2,'ALLEN',1600,null,'SALESMAN','15-JAN-87',20);
INSERT INTO EMP VALUES(3,'KING',5000,300,'PRESIDENT','20-FEB-92',30);
INSERT INTO EMP VALUES(4,'WARD',2975,125,'CLERK','17-MAR-84',10);
INSERT INTO EMP VALUES(5,'REMEO',3000,1400,'SALESMAN','26-APR-81',20);
INSERT INTO EMP VALUES(6,'JULITES',2600,NULL,'MANAGER','15-MAR-85',10);
```

## Queries

### Retrieve all records
```sql
SELECT * FROM EMP;
```

### Employees with salary greater than 1000
```sql
SELECT * FROM EMP WHERE SAL > 1000;
```

### Details of SALESMANs
```sql
SELECT ENAME, SAL, DEPTNO FROM EMP WHERE JOB = 'SALESMAN';
```

### Details of employee named SMITH
```sql
SELECT * FROM EMP WHERE ENAME = 'SMITH';
```

### Employees hired after 31st December 1980
```sql
SELECT ENAME, HIEREDATE
FROM EMP
WHERE (HIEREDATE, 'DD-MON-YY') > ('31-DEC-1980', 'DD-MON-YY');
```

### Employees hired before 1st January 1987
```sql
SELECT * FROM EMP WHERE (HIEREDATE, 'DD-MON-YY') < ('01-JAN-1987', 'DD-MON-YY');
```

### Annual salary of SMITH
```sql
SELECT SAL * 12 AS ANNUAL_SAL FROM EMP WHERE ENAME = 'SMITH';
```

### PRESIDENT(s) in departments 10 or 20
```sql
SELECT * FROM EMP WHERE (DEPTNO = 10 OR DEPTNO = 20) AND JOB = 'PRESIDENT';
```

### Details of CLERKs
```sql
SELECT * FROM EMP WHERE JOB = 'CLERK';
```

### Salaries of SALESMANs
```sql
SELECT SAL FROM EMP WHERE JOB = 'SALESMAN';
```

### Employees with salary greater than 2000
```sql
SELECT * FROM EMP WHERE SAL > 2000;
```

### PRESIDENT(s) with salary greater than 400
```sql
SELECT * FROM EMP WHERE SAL > 400 AND JOB = 'PRESIDENT';
```

### Annual salary of MANAGER(s) in department 10
```sql
SELECT ENAME, SAL * 12 AS ANNUAL_SAL FROM EMP WHERE JOB = 'MANAGER' AND DEPTNO = 10;
```

### Employees from departments 10, 20, or 30
```sql
SELECT * FROM EMP WHERE DEPTNO = 10 OR DEPTNO = 20 OR DEPTNO = 30;
```

### Employees with job titles SALESMAN or ANALYST
```sql
SELECT * FROM EMP WHERE JOB = 'SALESMAN' OR JOB = 'ANALYST';
```
