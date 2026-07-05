# SQL_assignment


1) Write a Query to display all the details of employee if the salary ranges between 500 and 250
and department number either 10, 20, 30.

select * from emp
-> where sal between 250 and 500
-> and deptno in (10,20,30);
Empty set (0.0017 sec)


2) Write a Query to display all the employee who belongs to department number 10 or 20 and
comm between 1000 and 3000 and were hired during 1980 to 1983.

 SELECT *
-> FROM emp
-> WHERE (deptno = 10 OR deptno = 20)
-> AND comm BETWEEN 1000 AND 3000
-> AND hiredate BETWEEN '1980-01-01' AND '1983-12-31';
Empty set (0.0020 sec)


3) Write a Query to display all the details of employee if he is not having the reporting manager.

select * from emp where mgr is null;
+-------+-------+-----------+------+------------+---------+------+--------+
| EMPNO | ENAME | JOB       | MGR  | HIREDATE   | SAL     | COMM | DEPTNO |
+-------+-------+-----------+------+------------+---------+------+--------+
|  7839 | KING  | PRESIDENT | NULL | 1981-11-17 | 5000.00 | 0.00 |     10 |
+-------+-------+-----------+------+------------+---------+------+--------+
1 row in set (0.0011 sec)



4) List the employee where salary is between 2000 and 3000.

select * from emp
-> where sal between 2000 and 1000;
Empty set (0.0017 sec)


5) List all the salesman in department number 30 and having salary greater than 5000.

select * from emp
-> where deptno=30
-> and sal >5000;
Empty set (0.0090 sec)


6) List all the employees who are having reporting manager in department 10.

 select * from emp
 -> where mgr is not null
 -> and deptno=10;
+-------+--------+---------+------+------------+---------+------+--------+
| EMPNO | ENAME  | JOB     | MGR  | HIREDATE   | SAL     | COMM | DEPTNO |
+-------+--------+---------+------+------------+---------+------+--------+
|  7782 | CLARK  | MANAGER | 7839 | 1981-06-09 | 2450.00 | 0.00 |     10 |
|  7934 | MILLER | CLERK   | 7782 | 1982-01-23 | 1300.00 | 0.00 |     10 |
+-------+--------+---------+------+------------+---------+------+--------+
2 rows in set (0.0012 sec)


7) Write a Query to display all the details of the employee if their job is having one _
(underscore) in it.

 select * from emp
-> where job LIKE
-> '%@_%' ESCAPE '@';
Empty set (0.0065 sec)


8) Write a Query to display who are having % in their names.

select * from emp where ename like '\%\' escape';
Empty set (0.0010 sec)

9) Write a Query to display who are having _(underscore) as second character in their name.

 select * from emp
-> where ename like '@_%' escape '@';
Empty set (0.0018 sec)

10) Write a Query to display all the employee who are getting some comm with their
designation is neither manager nor analyst.

 SELECT * FROM emp WHERE comm IS NULL AND job NOT IN ('MANAGER', 'ANALYST');
Empty set (0.0016 sec)

11) Write a Query to display all the manager whose annual salary is ending with 0.

SELECT *
-> FROM emp
-> WHERE job = 'MANAGER'
-> AND (sal * 12) LIKE '%0';
+-------+-------+---------+------+------------+---------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL     | COMM | DEPTNO |
+-------+-------+---------+------+------------+---------+------+--------+
|  7566 | JONES | MANAGER | 7839 | 1981-04-02 | 2975.00 | 0.00 |     20 |
|  7698 | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850.00 | 0.00 |     30 |
|  7782 | CLARK | MANAGER | 7839 | 1981-06-09 | 2450.00 | 0.00 |     10 |
+-------+-------+---------+------+------------+---------+------+--------+

12.DISPLAY THE LIST OF EMPLOYEES WHO HAVE JOINED A COMPANY BEFORE 1980 OR AFTER
1988.
 SELECT *
  -> FROM emp
  -> WHERE job = 'MANAGER'
  -> AND (sal * 12) LIKE '%0';
+-------+-------+---------+------+------------+---------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL     | COMM | DEPTNO |
+-------+-------+---------+------+------------+---------+------+--------+
|  7566 | JONES | MANAGER | 7839 | 1981-04-02 | 2975.00 | 0.00 |     20 |
|  7698 | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850.00 | 0.00 |     30 |
|  7782 | CLARK | MANAGER | 7839 | 1981-06-09 | 2450.00 | 0.00 |     10 |
+-------+-------+---------+------+------------+---------+------+--------+
13.DISPLAY THE LIST OF EMPLOYEES WHO HIRED DURING BEFORE 1982 AND AFTER 1985.
 SELECT *
 -> FROM emp
-> WHERE hiredate < '1980-01-01'
-> OR hiredate > '1988-12-31';
Empty set (0.0087 sec)
14.WAQTD THE NAMES OF THE EMPLOYEES WORKING IN DEPT 10,20,40 OR EMPLOYEE
WORKING AS CLERK,SALESMAN,ANALYST.

 > SELECT ename
-> FROM emp
-> WHERE deptno IN (10,20,40)
-> OR job IN ('CLERK','SALESMAN','ANALYST');
+--------+
| ename  |
+--------+
| SMITH  |
| ALLEN  |
| WARD   |
| JONES  |
| MARTIN |
| CLARK  |
| SCOTT  |
| KING   |
| TURNER |
| ADAMS  |
| JAMES  |
| FORD   |
| MILLER |
+--------+
15.WAQTD THE NAME OF THE EMPLOYEES WHOSE NAME STARTS WITH 'S' AND HAVING FIVE
CHARACTERS.
SELECT ename
-> FROM emp
-> WHERE ename LIKE 'S____';
+-------+
| ename |
+-------+
| SMITH |
| SCOTT |
+-------+
16.WAQTD THE NAME OF THE EMPLOYEES WHO ARE NOT GET COMM AND WORKING DEPTNO
10,20.
 SELECT ename
-> FROM emp
-> WHERE comm IS NULL
-> AND deptno IN (10,20);
Empty set (0.0071 sec)
17.WAQTD DETAILS OF THE EMPLOYEES ALONG WITH ANNUAL SALARY IF THEY ARE WORKING
DEPT MANAGER AS 20,30 AND THEIR ANNUAL SALARY GREATER THAN 12000.
SELECT emp.*, sal*12 AS annual
-> FROM emp
-> WHERE job = 'MANAGER'
-> AND deptno IN (20,30)
-> AND sal*12 > 12000;
+-------+-------+---------+------+------------+---------+------+--------+---------------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL     | COMM | DEPTNO | annual_salary |
+-------+-------+---------+------+------------+---------+------+--------+---------------+
|  7566 | JONES | MANAGER | 7839 | 1981-04-02 | 2975.00 | 0.00 |     20 |      35700.00 |
|  7698 | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850.00 | 0.00 |     30 |      34200.00 |
+-------+-------+---------+------+------------+---------+------+--------+---------------+
18.WAQTD DETAILS OF EMPLOYEES WHO ARE HIRED FEB.
 SELECT *
-> FROM emp
-> WHERE MONTH(hiredate) = 2;
+-------+-------+----------+------+------------+---------+--------+--------+
| EMPNO | ENAME | JOB      | MGR  | HIREDATE   | SAL     | COMM   | DEPTNO |
+-------+-------+----------+------+------------+---------+--------+--------+
|  7499 | ALLEN | SALESMAN | 7698 | 1981-02-20 | 1600.00 | 300.00 |     30 |
|  7521 | WARD  | SALESMAN | 7698 | 1981-02-22 | 1250.00 | 500.00 |     30 |
+-------+-------+----------+------+------------+---------+--------+--------+
2 rows in set (0.0018 sec)
19.WAQTD DETAILS OF EMPLOYEES ALONG WITH ANNUAL SALARY WHOSE NAME STARTS 'M'
AND LAST BUT FIRST CHARACTER 'S'.
SELECT emp.*, sal*12 AS annual_salary
-> WHERE ename LIKE 'M%S_';
Empty set (0.0017 sec)
20.WAQTD NAME OF EMPLOYEES WHOSE NAME STARTS VOWELS AND NOT HAVE REPORTING
MANAGER.
 SELECT ename
 -> FROM emp
-> WHERE mgr IS NULL
-> AND (ename LIKE 'A%'
-> OR ename LIKE 'E%'
-> OR ename LIKE 'I%'
-> OR ename LIKE 'O%'
-> OR ename LIKE 'U%');
Empty set (0.0014 sec)
21.WAQTD NAME AND HIREDATE OF EMPLOYEES WHO ARE HIRED BETWEEN JAN-81 AND DEC-
81
SELECT ename, hiredate
-> FROM emp
-> WHERE hiredate BETWEEN '1981-01-01' AND '1981-12-31';
+--------+------------+
| ename  | hiredate   |
+--------+------------+
| ALLEN  | 1981-02-20 |
| WARD   | 1981-02-22 |
| JONES  | 1981-04-02 |
| MARTIN | 1981-09-28 |
| BLAKE  | 1981-05-01 |
| CLARK  | 1981-06-09 |
| KING   | 1981-11-17 |
| TURNER | 1981-09-08 |
| JAMES  | 1981-12-03 |
| FORD   | 1981-12-03 |
+--------+------------+
10 rows in set (0.0015 sec)
22.WAQTD SALESMAN DETAILS.
SELECT *
-> FROM emp
-> WHERE job = 'SALESMAN';
+-------+--------+----------+------+------------+---------+---------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL     | COMM    | DEPTNO |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600.00 |  300.00 |     30 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00 |  500.00 |     30 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00 |    0.00 |     30 |
+-------+--------+----------+------+------------+---------+---------+--------+
4 rows in set (0.0012 sec)
23.WAQTD DEPT DETAILS OF 10,20,30.
 select * from dept
-> where deptno in (10,20,30);
+--------+------------+----------+
| DEPTNO | DNAME      | LOC      |
+--------+------------+----------+
|     10 | ACCOUNTING | NEW YORK |
|     20 | RESEARCH   | DALLAS   |
|     30 | SALES      | CHICAGO  |
+--------+------------+----------+
24.WAQTD PLACE OF PRESIDENT.
SELECT d.loc
-> FROM emp e
-> JOIN dept d
-> ON e.deptno = d.deptno
-> WHERE e.job = 'PRESIDENT';
+----------+
| loc      |
+----------+
| NEW YORK |
+----------+
1 row in set (0.0014 sec)

25.WAQTD THE DETAILS OF EMPLOYESS ALONG WITH HALF TERM SALARY WHO EARNIG SAL
GREATER THAN 5000 AND NAME STARTS WITH VOWELS.
SELECT emp.*, sal*6 AS half_term_salary
 -> FROM emp
 -> WHERE sal > 5000
 -> AND (ename LIKE 'A%'
 -> OR ename LIKE 'E%'
 -> OR ename LIKE 'I%'
 -> OR ename LIKE 'O%'
 -> OR ename LIKE 'U%');
Empty set (0.0073 sec)

26.WAQTD DETAILS OF EMPLOYESS WHO ARE NOT WORKING AS A MANAGER AND HAVING SAL
IN BETWEEN 1000-2000.
SELECT *
-> FROM emp
-> WHERE job <> 'MANAGER'
-> AND sal BETWEEN 1000 AND 2000;
+-------+--------+----------+------+------------+---------+---------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL     | COMM    | DEPTNO |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600.00 |  300.00 |     30 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00 |  500.00 |     30 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00 |    0.00 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1987-05-23 | 1100.00 |    0.00 |     20 |
|  7934 | MILLER | CLERK    | 7782 | 1982-01-23 | 1300.00 |    0.00 |     10 |
+-------+--------+----------+------+------------+---------+---------+--------+

27.WAQTD LIST OF EMPLOYEES WITH ANNUAL SALARY WHOSE ANNUAL SALARY IS 4LPA.
 SELECT ename, sal, sal*12 AS annual_salary
-> FROM emp
-> WHERE sal*12 = 400000;
Empty set (0.0012 sec)
28.WAQTD NAME OF EMPLOYEES WHO IS WORKING AS A CLERKS OR PRESIDENT.
SELECT ename
-> FROM emp
-> WHERE job IN ('CLERK', 'PRESIDENT');
+--------+
| ename  |
+--------+
| SMITH  |
| KING   |
| ADAMS  |
| JAMES  |
| MILLER |
+--------+
5 rows in set (0.0012 sec)
29.WAQTD LIST OF EMPLOYEES WHOSE SALARY RANGE BETWEEN 0-1400.
SELECT *
-> FROM emp
-> WHERE sal BETWEEN 0 AND 1400;
+-------+--------+----------+------+------------+---------+---------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL     | COMM    | DEPTNO |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7369 | SMITH  | CLERK    | 7902 | 1980-12-17 |  800.00 |    0.00 |     20 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00 |  500.00 |     30 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1987-05-23 | 1100.00 |    0.00 |     20 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 |  950.00 |    0.00 |     30 |
|  7934 | MILLER | CLERK    | 7782 | 1982-01-23 | 1300.00 |    0.00 |     10 |
+-------+--------+----------+------+------------+---------+---------+--------+
6 rows in set (0.0019 sec)
30.WAQTD NAMES OF EMPLOYEES WHO'S WORKING IN DEPT 10 AND HAVING SECOND LETTER
AS 'M'.
SELECT ename
-> FROM emp
-> WHERE deptno = 10
-> AND ename LIKE '_M%';
Empty set (0.0014 sec)
31.WAQTD THE MAXIMUM SALARY OF DEPT 30 AND 20.
SELECT deptno, MAX(sal) AS max_salary
-> FROM emp
-> WHERE deptno IN (20,30)
-> GROUP BY deptno;
+--------+------------+
| deptno | max_salary |
+--------+------------+
|     20 |    3000.00 |
|     30 |    2850.00 |
+--------+------------+
32.WAQTD NAME OF THE EMPLOYEE WHO'S GETTING SALARY LESS THAN SMITH.
SELECT ename
-> FROM emp
-> WHERE sal < (
-> SELECT sal
-> FROM emp
-> WHERE ename = 'SMITH'
-> );
Empty set (0.0079 sec)
33.WAQTD NUMBER OF TIMES THE SALARIES PRESENT IN EMPLOYEE TABLE.
 SELECT sal, COUNT(*) AS no_of_times
 -> FROM emp
 -> GROUP BY sal;
+---------+-------------+
| sal     | no_of_times |
+---------+-------------+
|  800.00 |           1 |
| 1600.00 |           1 |
| 1250.00 |           2 |
| 2975.00 |           1 |
| 2850.00 |           1 |
| 2450.00 |           1 |
| 3000.00 |           2 |
| 5000.00 |           1 |
| 1500.00 |           1 |
| 1100.00 |           1 |
|  950.00 |           1 |
| 1300.00 |           1 |
+---------+-------------+
34.WAQTD MINIMUM SALARIES GIVEN TO AN EMPLOYEE WORKING IN EACH DEPT.
SELECT deptno, MIN(sal) AS minimum_salary
-> FROM emp
-> GROUP BY deptno;
+--------+----------------+
| deptno | minimum_salary |
+--------+----------------+
|     10 |        1300.00 |
|     20 |         800.00 |
|     30 |         950.00 |
+--------+----------------+
35.LIST ALL THE DEPT NAME THAT ARE HAVING ATLEAST 3 EMPLOYEES BUT NOT MORE THAN 5
EMPLOYEES IN IT.
SELECT d.dname
-> FROM dept d
-> JOIN emp e
-> ON d.deptno = e.deptno
-> GROUP BY d.deptno, d.dname
-> HAVING COUNT(*) BETWEEN 3 AND 5;
+------------+
| dname      |
+------------+
| ACCOUNTING |
| RESEARCH   |
+------------+
36.WAQTD NUMBER OF EMPLOYEES WORKING IN EACH DEPARTMENT EXCEPT SALESMAN.
SELECT deptno, COUNT(*) AS no_of_employees
-> FROM emp
-> WHERE job <> 'SALESMAN'
-> GROUP BY deptno;
+--------+-----------------+
| deptno | no_of_employees |
+--------+-----------------+
|     10 |               3 |
|     20 |               5 |
|     30 |               2 |
+--------+-----------------+
37.WAQTD DETAILS OF EMPLOYEES WHO ARE GETTING THE REPEATED SALARY.
SELECT *
-> FROM emp
-> WHERE sal IN (
-> SELECT sal
-> FROM emp
-> GROUP BY sal
-> HAVING COUNT(*) > 1
-> );
+-------+--------+----------+------+------------+---------+---------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL     | COMM    | DEPTNO |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00 |  500.00 |     30 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
|  7788 | SCOTT  | ANALYST  | 7566 | 1987-04-19 | 3000.00 |    0.00 |     20 |
|  7902 | FORD   | ANALYST  | 7566 | 1981-12-03 | 3000.00 |    0.00 |     20 |
+-------+--------+----------+------+------------+---------+---------+--------+
38.WAQTD NUMBER OF EMPLOYESS WHO ARE HAVING SAME NAME
SELECT ename, COUNT(*) AS total
-> FROM emp
-> GROUP BY ename
-> HAVING COUNT(*) > 1;
Empty set (0.0015 sec)

39.WAQTD AVG SALARY NEEDED TO PAY ALL THE EMPLOYEES IN EACH DEPT EXCLUDING THE
EMPLOYEES OF DEPT 10.
40.WAQTD NAME AND TOTAL SALARY ODF THE EMPLOYEES IF THE EMPLOYEES ARE EARNING
MORE THAN 2500.
41.DISPLAY LOCATION AND DNAME OF EMPLOYEE WHO ARE WORKING AS PRESIDENT WITH
1500 SALARY.
42.WAQTD ALL THE EMPLOYEES WHOSE JOB NOT SAME AS SCOTT AND SALARY IS GREATER
THAN ALLEN.
43.LIST DEPT NAME HAVING ATLEAST 3 SALESMAN.
44.DISPLAY ALL THE EMPLOYEES WHO'S DEPT NAME ENDS WITH 'S'.
45.WAQTD JOB AND MAX SAL OF EMPLOYEE IN EACH JOB IF THE MAX SAL EXCEEDS 3000 ON
EACH DEPT.
46.WAQTD DEPT NAME WHO'S HAVING HIGHEST COMMISSION.
47.WAQTD THE EMPLOYEE NAME WHOSE DEPT NAME HAS 2ND CHARACTER AS 'O'.
48.WAQTD NAMES OF THE EMPLOYEES EARNING GREATER THAN MILLER.
49.WAQTD NAME AND HIREDATE OF THE EMPLOYEES IF THE EMPLOYEE WAS HIRED AFTER
JONES.
50.WAQTD ALL THE DEATILS OF EMPLOYEES WORKING AS SALESMAN IN THE DEPT 20 ABD
EARNING COMM MORE THAN SMITH AND HIRED AFTER KING.
51.WAQTD NAMES OF THE EMPLOYEES EARNING MORE THAN SMITH IN SALES DEPT.
52.WAQTD DETAILS OF THE EMPLOYEES WORKING AS ANALYST IN THE LOCATION DALLAS.
53.DISPLAY ALL THE EMPLOYEES WHOSE LOCATION NAME ENDING WITH 'S'.
54.WAQTD NAME , ANNUAL SALARY OF THE EMPLOYEES IF THEIR ANNUAL SALARY IS MORE
THAN ALL THE MANAGER.
55.WAQTD DETAILS OF EMPLOYESS WHOSE HIREDATE GREATER THAN SALESMAN.
56.WAQTD THE PRESIDENT SALARY.
57.WAQTD THE COUNT OF EMP IN EACH DEPT.
58.WAQTD THE DNAME OF EMP OF EACH DEPT.






