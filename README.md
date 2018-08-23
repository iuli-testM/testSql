-Give me Second Highest salary from all the employee
select Salary from Salary order by Salary desc limit 1 OFFSET 1 ;
-Give me second last lowest salary from all the employee
select Salary from Salary order by Salary asc limit 1 OFFSET 1 ;
-Give me average salary of a each Department
select Employe.deptId,  avg(Salary.Salary) as "Average salary" from Salary join Employe on Employe.EmpId = Salary.EmpId group by Employe.deptId ;
-Give me output in format as below
Employee Id, Emp Name, Dept Name, Salary
select e.empId as "Employee Id", e.EmpName as "Emp Name", d.DeptName as "Dept Name",
s.Salary from Employe as e, Department as d, Salary as s where s.EmpId = e.EmpId and e.deptId = d.deptId; 

-Give me employees which doesn’t belong to any Department
select Employe.EmpName from Employe left join Department on Department.deptId = Employe.deptId where Department.deptId is NULL;
-Give me employees which doesn’t have manager
select EmpName from Employe where mangerEmpId is NULL;