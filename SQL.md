# Table Join

```
select first_name,item from Customers
join Orders where Customers.customer_id==Orders.customer_id
```

# Second highest age

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

# Explain indexing in a database.

Classic example **"Index in Books"**

# Difference between clustered and non-clustered index.

* Clustered indexes sort and store the data rows in the table or view based on their key values. These key values are the columns included in the index definition. There can be only one clustered index per table, because the data rows themselves can be stored in only one order.
* The only time the data rows in a table are stored in sorted order is when the table contains a clustered index. When a table has a clustered index, the table is called a clustered table. If a table has no clustered index, its data rows are stored in an unordered structure called a heap.
* Nonclustered indexes have a structure separate from the data rows. A nonclustered index contains the nonclustered index key values and each key value entry has a pointer to the data row that contains the key value.
* The pointer from an index row in a nonclustered index to a data row is called a row locator. The structure of the row locator depends on whether the data pages are stored in a heap or a clustered table. For a heap, a row locator is a pointer to the row. For a clustered table, the row locator is the clustered index key.
* You can add nonkey columns to the leaf level of the nonclustered index to by-pass existing index key limits, and execute fully covered, indexed, queries. For more information, see [Create indexes with included columns](https://learn.microsoft.com/en-us/sql/relational-databases/indexes/create-indexes-with-included-columns?view=sql-server-ver16). For details about index key limits, see [Maximum capacity specifications for SQL Server](https://learn.microsoft.com/en-us/sql/sql-server/maximum-capacity-specifications-for-sql-server?view=sql-server-ver16).

# VIEW

CREATE VIEW sales_employees AS
SELECT name, salary
FROM employees
WHERE department = 'Sales';

# PROCEDURE

CREATE PROCEDURE sales_employees AS

BEGIN
SELECT name, salary
FROM employees
WHERE department = 'Sales';

END

# Temporary Table

A temporary table in SQL is a table that exists temporarily and is typically used to store intermediate results that you need to access multiple times within a session.

CREATE TABLE #TempTable (
    ID INT PRIMARY KEY,
    Name NVARCHAR(50),
    Age INT
);
