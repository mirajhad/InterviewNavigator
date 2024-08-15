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

---
