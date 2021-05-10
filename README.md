# Submission
Question 1:
a.	The problem with using the average is that it can be totally skewed by a small number of data points with very large deviations (outliers). For example, the customer with shop_id 42 has ordered thousands of items, which gives a very huge order value, unlike the rest of the customers whose orders contain less than 10 total_items.	

There are two ways to better evaluate this data. The first way is that we can remove the outliers before calculating an average. The second way is that we can use the median value.

b.	After removing the outliers, the mean can still be skewed by the points that fall extreme points values and may not represent most orders. Using the median to report for the dataset will ensure that the representative value will not be skewed by largely deviating points.

c.	The median order value is $284.

Question 2:
a)	54

SELECT count (*) FROM [Orders] where ShipperID==1;

b)	Peacock
SELECT COUNT(Orders.OrderID) AS Counts ,Employees.LastName

FROM Orders

INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID

GROUP BY Employees.EmployeeID

ORDER BY Counts DESC;

c)	Gumbär Gummibärchen

SELECT SUM(OrderDetails.Quantity) AS Counts,Products.ProductName

FROM ((Products

INNER JOIN Suppliers ON  Products.SupplierID=Suppliers.SupplierID)

INNER JOIN OrderDetails ON Products.ProductID=OrderDetails.ProductID)

WHERE Suppliers.Country LIKE 'Germany'GROUP BY Products.ProductName

ORDER BY Counts DESC;
