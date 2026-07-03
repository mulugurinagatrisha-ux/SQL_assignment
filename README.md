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

