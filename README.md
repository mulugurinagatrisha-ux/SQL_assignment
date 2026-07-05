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






