# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),
Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### TABLE:
![table](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/eb824328-342f-4dd0-8036-a5bdf1b745ed)

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary = salary + (salary * 0.10);
```
### OUTPUT:
![1](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/51da1035-97e4-4093-a6c9-442cea45fba6)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```
DELETE FROM manager WHERE salary < 2750;
```
### OUTPUT:
![2](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/2a1524fb-19bc-4aac-8003-3d1c9f26187f)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```
SELECT ename AS "Name", salary * 12 AS "Annual Salary" from manager;
```
### OUTPUT:
![3](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/87c1238b-91dc-46d1-8b0e-9e7bc5ca4105)

### Q4)	List the names of Clerks from emp table.

### QUERY:
```
SELECT ename from manager where designation='clerk';
```
### OUTPUT:
![4](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/bc150117-a04e-4980-bba7-ad30fa12e5ab)

### Q5)	List the names of employee who are not Managers.

### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![5](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/8d35c5aa-84a7-4625-9bd5-d99490fb9f77)

### Q6)	List the names of employees not eligible for commission.

### QUERY:
```
SELECT ename from manager where commission=0;
```
### OUTPUT:
![6](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/20b9d46b-6650-403c-bbe2-0bb479ac9861)

### Q7)	List employees whose name either start or end with ‘s’.

### QUERY:
```
SELECT enameFROM manager WHERE ename LIKE 'S%' OR ename LIKE '%s';
```
### OUTPUT:
![7](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/8cfd2975-09f7-4065-9e1c-4ccb5bd33784)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```
select ename,designation,deptno,Hiredate from manager order by Hiredate asc;
```
### OUTPUT:
![8](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/99e008c4-f264-4414-9a57-437f5672e109)

### Q9) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```
 SELECT * FROM manager WHERE Hiredate < DATE '1981-09-30';
```
### OUTPUT:
![9](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/1b791cd9-40b2-412f-8e3d-72c7b71273df)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```
select ename,deptno,salary from manager order by deptno asc;
select ename,deptno,salary from manager order by salary desc;
```
### OUTPUT:
![10](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/2c5233ab-203a-4b13-a938-67d782b40103)

### Q11) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```
select ename from manager where deptno not in (10,30,40);
```
### OUTPUT:
![11](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/c8a630b0-411a-4326-b2b0-ba7909945666)

### Q12) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```
### OUTPUT:
![12](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/13bf5e9d-5d48-43ff-8325-34e5be532f80)

### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select ename ,salary,annualsalary from manager where salary = (select max(salary) from manager);
select ename ,salary,annualsalary from manager where salary = (select min(salary) from manager);
select avg(salary) from manager;
```
### OUTPUT:
![13](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/88cff015-95ee-424f-bbdf-8608c126cd95)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation, COUNT(*) AS "Number of Employees" FROM manager GROUP BY designation ORDER BY COUNT(*) DESC;
```
### OUTPUT:
![14](https://github.com/Divya110205/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119404855/775bbaef-a6aa-4351-a915-936efa8d9be9)
