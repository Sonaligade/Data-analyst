show databases;
use hr;
show tables;

## 1.Fetch all the records for Employees Table.
## Explain the meaning of “*”.
select * from employees;


##2. Show all the emp_id, first_name, last_name from employee Table.

select employee_id,first_name,last_name from employees;


#3.Write  a  query  in  SQL  to  display  the first_name  and  last_name,    department_id  and salary
#   from  employees  Table  who  earn  more  than  20000.
select * from employees;
select department_id,first_name,last_name,salary from employees where salary>20000;
select concat(first_name," ",last_name) as name,department_id,salary from employees where salary>20000;

##4.Write  a  query  in  SQL  to  display  the  first_name  and  last_name,  email,  salary  and manager_ID for those employees 
# whose managers_ID  is 120, 103 or 145.(18 rows)

select department_id,first_name,last_name,email,salary manager_id from employees where manager_id in(120,103,145);


##5.Write  a  query  in  SQL  to  display  the  first_name  and    last_name,department_id  and salary from employees Table   who earn more than 8000 And whose managers_ID  is 120, 103      or 145.(3 rows)

select first_name,last_name,email,salary from employees where  manager_id in(120,103,145) and salary>8000;


#6.Write a query to display all the locations (id, city) which do not have any state province mentioned.(6 rows)[NOTE: LOCATION TABLE]

select * from locations;
select location_id,city from locations where state_province is null;

#7.Write  a  query  to  display  job_id,job  titles,min_salary,max_salary  whose  maximum salary is greaterthan 10000. (9 rows) [NOTE:JOBS TABLE]
select * from jobs where max_salary>10000;



#8.Write   a   query   to   display   department_id,department_name,   Manager_id   whose manager_id  is  greater  than    200  and   location_id  is  2400.(1row)  [NOTE  : DEPARTMENTS TABLE]
select * from departments;
select department_id,department_name,location_id from departments where manager_id>200 and location_id=2400;


#•Explain why NULL is displayed here–this is a blank row displayed by MYSQL workbench





#9.Write a query to display the job title whose minimum  salary is greater than 8000 and max salary less than 20000 (3 rows).[NOTE : JOBS TABLE]

select job_title from jobs where min_salary>8000 and max_salary<20000;



#10.Write a query to retrieve all the records of departments with managers for the location id 1700. (5rows) [NOTE : DEPARTMENTS TABLE]

select * from departments where location_id=1700 and manager_id is not null;


#11.List all departments starting   with   “P”where    there    are managers.(2 rows)[NOTE:DEPARTMENT TABLE]

select * from departments where department_name like "P%" and manager_id is not null;

#12.Print a bonafide certificate for an employee (say for emp. id 123) as
#  below:#"This is to certify that <full name> with employee id <emp. id> is working as <job id> in dept. <dept ID>. (1 ROW) [NOTE : EMPLOYEES table].
select * from employees;

select concat("this is to certify that",first_name," ",last_name,"with employee id",employee_id,"is working as",job_id,"in dept.",department_id,".") 
as bonafide from employees where employee_id=123;

select concat("this is to certify that",first_name," ",last_name,"with employee id",employee_id,"is working as",job_id,"in dept.",department_id,".") 
as bonafide from employees;

#13.Display the first name where commission percentage is not provided.(72 rows)
select first_name from employees where commission_pct is null;

use hr;
select * from employees;


-- count
select count(*) from employees;
select count(*) as result from employees;
select count(*) as result from employees where salary>=10000;
select count(commission_pct) as entries from employees;
select count(*)-count(commission_pct) as entries from employees;

-- min,max,sum,avg
select min(salary),max(salary),sum(salary),avg(salary) from employees;
select min(commission_pct),max(commission_pct),sum(commission_pct),avg(commission_pct) from employees;

# applying num fun on aggregation fun
select min(salary) from employees where department_id=70;
select format(avg(salary),0) from employees;


select department_id,avg(salary) from employees group by department_id;

-- count number of employees in each department
select department_id,count(*) from employees group by department_id;

-- get min and max salary for each department
select department_id,min(salary),max(salary) from employees group by department_id;

-- get min max hire_date for each department
select department_id,min(hire_date),max(hire_date) from employees group by department_id;

-- for each manager,find the number of emp managed by them
select * from employees;
select manager_id,count(employee_id) from employees group by manager_id;

-- get the number of emp joined in each year
select year(hire_date),count(*) from employees group by year(hire_date);
select year(hire_date),count(*) from employees group by year(hire_date) order by year(hire_date);

-- query with where
select department_id,avg(salary) from employees where department_id is not null group by department_id;

select department_id,min(salary) from employees where salary>10000 group by department_id;

select job_id,count(distinct manager_id) from employees group by job_id;
select job_id,count(distinct department_id),count(distinct employee_id) from employees group by job_id;

select department_id,job_id,count(*);

select year(hire_date),month(hire_date),count(employee_id) from employees group by year(hire_date),month(hire_date);

select department_id,avg(salary) from employees where salary>6000 group by department_id;

select department_id,avg(salary) from employees where avg(salary) group by department_id; -- ERROR

select department_id,avg(salary) from employees group by department_id 
having avg(salary)>6000;


-- GET total and avg salaries with count of emp for each department  but only for job_id as'ad_vp','sa_rep'
-- arrange the result for each department in increasing oredr of total salary
select department_id,JOB_ID,SUM(salary),avg(salary),COUNT(*) from employees 
WHERE JOB_ID IN('AD_VP','SA_REP')
group by department_id,JOB_ID
ORDER BY SUM(SALARY);

-- 
select distinct substring(phone_number,1,3) from employees;

select count(manager_id),substr(phone_number,1,3),avg(salary) 
from employees group by substr(phone_number,1,3);




















