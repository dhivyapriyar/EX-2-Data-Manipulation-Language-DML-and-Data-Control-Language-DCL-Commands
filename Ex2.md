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
 create table manager(enumber int(6),ename char(15),salary int(5),commission int(4),annualsalary int(7),designation char(10),deptno int(2),reporting char(10));
```
## Q1) insert the following values into the table
```sql
insert into manager values(7369,'Dhivya',2500,500,30000,'clerk',10,'Swetha');
insert into manager values(7369,'Harini',2500,500,30000,'clerk',Null,'Yuva');
insert into manager values(7369,'Prabha',3500,100,40000,'clerk',11,'Raju');
insert into manager values(7369,'Thilaga',2000,1000,60000,'manager',12,'Vidhya');
```
### OUTPUT:
![2 1](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/37bdfc3b-bb09-4e74-9cca-a33e88da38f0)


### Q2) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*10/100);
```
### OUTPUT:
![2 2](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/09296247-ba19-4b90-9d54-d6adafaeb1bc)

### Q3) Delete the records from manager table where the salary less than 2500..


### QUERY:
```
 delete from manager where salary<2500;
```

### OUTPUT:
![2 3](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/bd81e32b-e007-4a71-a3e3-936cecf32050)

### Q4) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual Salary" from manager;
```

### OUTPUT:
![2 4](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/1371d556-177d-4fb5-98e1-4129ed96a7e3)


### Q5)	List the names of Clerks from emp table.


### QUERY:
```
 select ename from manager where designation='clerk';
```

### OUTPUT:
![2 5](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/a6bbfc0f-0fe1-484e-a534-5badec21fda0)


### Q6)	List the names of employee who are not Manager.


### QUERY:
```
select ename from manager where designation!='manager';
```

### OUTPUT:
![2 6](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/5cdab9e6-c416-4e31-8ec6-f43487b669ff)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
 select ename from manager where commission=0;
```


### OUTPUT:
![2 7](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/22b6a2c2-16e3-4db9-944f-49042ab49384)





### Q8) List the Details of Employees whose salary is more than 30000.


### QUERY:
```
select * from manager where annualsalary>30000;
```

### OUTPUT:
![2 10](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/6d319e5c-5d01-4e9a-8173-bb6f765b5f97)


### Q9) To count the number of rows present.


### QUERY:
```
select count(*) as rownumber from manager;
```

### OUTPUT:
![2 11](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/481fd478-a73d-46b5-8c1d-4daac478c368)


### Q10) List the names of employees not belonging to dept no 10


### QUERY:
```
 select ename from manager where deptno NOT IN (10);
```

### OUTPUT:
![2 12](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/bade32f8-33ef-4082-8a42-cbf19a970adf)

### Q11) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from manager;
```

### OUTPUT:
![2 11](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/3060da67-aa4f-4e3c-a95b-c468ad8c490b)


### Q12) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select max(salary) as maximumsal,min(salary) as minimumsal,avg(salary) as averagesal from manager;
```


### OUTPUT:
![2 13](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/ddc9fed0-3444-4bb8-80b1-6ebcfd75cdff)


### Q13) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```

### OUTPUT:
![image](https://github.com/dhivyapriyar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477552/7d30db0e-cd9e-4007-b28b-6dbc3a327c33)

### RESULT:
Thus the DML command was executed successfully.
