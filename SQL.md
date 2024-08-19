Second highest age

SELECT DISTINCT AGE

FROM Customers

ORDER BY AGE DESC

OFFSET 1ROWS

FETCHNEXT1ROWS ONLY

++++++++++++++++++++++++++++++++++++++++

 SELECTTOP1 AGE FROM (

 SELECT  TOP2  AGE FROM Customers ORDER BY AGE DESC

 ) AS INNERQUERY ORDER BY AGE ASC

---

EmpId   Name   ManagerId

1 John 3

2 Naresh Null

3 Mike 2

Mike - Naresh

Jhon- Mike

Naresh-null

SELECT E1.Name AS Employee, E2.Name AS Manager

FROM YourTableName E1

LEFT JOIN YourTableName E2 ON E1.ManagerId = E2.EmpId;

---

SELECT*

FROM Orders

INNER JOIN Customers ON Orders.customer_id = Customers.customer_id;


# Delete Columns of a Table

```sql
ALTER TABLE dbo.Employee
DROP COLUMN Address, Phone, Email;
```

# Rename Table

```sql
EXEC sp_rename 'Employee', 'Consultant';
```

# Find Year

```
SELECT DATEDIFF(yy, '1995-12-31', '2024-08-20') AS DaysBetween;
```

## Update Multiple Columns

```sql
UPDATE Employee
SET Email = 'jb007@test.com', Phone = '111.111.0007', HireDate='05-23-2001'
WHERE EmployeeID = 3;
```

# GROUP BY

```sql
SELECT DeptId, COUNT(EmpId) as 'Number of Employees' 
FROM Employee
GROUP BY DeptId;

--following query will return same data as above
SELECT DeptId, COUNT(*) as 'No of Employees' 
FROM Employee
GROUP BY DeptId;
```

## Create a Primary Key in an Existing Table

```sql
ALTER TABLE Employee
ADD CONSTRAINT PK_Employee_EmployeeID PRIMARY KEY (EmployeeID)
```

# Delete a Primary Key

```sql
ALTER TABLE Employee 
DROP CONSTRAINT PK_Employee_EmployeeID;   
```

# Create a Foreign Key

```sql
CREATE TABLE Employee(
EmployeeID int IDENTITY (1,1) NOT NULL,
FirstName nvarchar (50) NOT NULL,
LastName nvarchar (50) NOT NULL,
DepartmentID int NULL, 
CONSTRAINT PK_EmployeeID PRIMARY KEY (EmployeeID), 
CONSTRAINT FK_Employee_Department FOREIGN KEY (DepartmentID)
REFERENCES Department (DepartmentID)
ON DELETE CASCADE
ON UPDATE CASCADE)
```

# Delete a Foreign Key

```sql
ALTER TABLE Employee   
DROP CONSTRAINT FK_Employee_Department
```

# Candidate Vs Primary

`Candidate Key` – A Candidate Key can be any column or a combination of columns that can  **qualify as unique key in database** . There can be multiple Candidate Keys in one table. Each Candidate Key can qualify as Primary Key.

`Primary Key` – A Primary Key is a column or a combination of columns that  **uniquely identify a record** . Only one Candidate Key can be Primary Key.
