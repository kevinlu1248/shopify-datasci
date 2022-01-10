# Summer 2022 Data Science Intern Challenge 

## Question 1
All of question 1 is answered in the notebook `main.ipynb`. The required dependencies are all included under `requirements.txt`.

## Question 2

a)
```sql
SELECT COUNT(*) FROM Orders;
```
**196**

b)
```sql
SELECT       EmployeeID
    FROM     Orders
    GROUP BY EmployeeID
    ORDER BY COUNT(*) DESC
    LIMIT    1;
```
4
```sql
SELECT LastName FROM Employees where EmployeeID=4;
```
**Peacock**

c)
```sql
SELECT ProductID
FROM OrderDetails as order_detail
WHERE EXISTS (SELECT *
    FROM Orders as order_obj
    WHERE 
        order_detail.OrderID=order_obj.OrderID
        AND
        EXISTS (SELECT *
        FROM Customers as customer
        WHERE order_obj.CustomerID=customer.CustomerID AND customer.Country="Germany"))
GROUP BY ProductID
ORDER BY COUNT(*) DESC
LIMIT 1
```
34
```sql
SELECT ProductName FROM Products WHERE ProductID=31
```
**Gorgonzola Telino**
