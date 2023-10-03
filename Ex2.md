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
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/6081a60a-a55c-4c03-a23e-77be461c4811)


### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update managers set salary=salary+(salary*10/100);
```
### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/39403a8c-0efa-46da-a6f8-5cdd10622d44)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete managers where salary<2750;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/6a204637-a800-4b1b-b71a-e53dc7bcbfae)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/2abe8856-9b5c-4bce-bbd3-ee0671a8f534)


### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from managers where designation='clerk';
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/898253b4-5ff9-4ba8-9cd9-c405539f3901)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from managers where designation!='manager';
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/04b0bbcb-ec02-4664-a8aa-607f9e6316d8)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from managers where commission=0;
```


### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/673b5038-b00f-4d83-861c-00e003f3336a)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/9717224b-dbec-4339-a733-ca126dd4fc2a)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/4cb8f738-0aa8-4a8f-ac21-b7ca07f296c7)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/88e0ac81-3d00-4e2a-8760-47651968aaca)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/f4fbd303-6a26-493f-82ed-40d3e91d90ab)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/7ee66b84-d51e-4793-8027-e8f4974db01e)

### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from managers;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/f6a2f277-76ac-447b-a422-58c93294406f)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```


### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/f74079ea-f63f-4542-ab84-21f3363e918f)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/7d30db0e-cd9e-4007-b28b-6dbc3a327c33)
