# Simple solutions to 50 NorthwindDB questions 

#### Create a report that shows the CategoryName and Description from the categories table sorted by CategoryName
SELECT categoryname, description <br>
FROM categories  <br>
ORDER BY categoryname;


#### Create a report that shows the ContactName, CompanyName, ContactTitle and Phone number from the customers table sorted by Phone
SELECT contactname, companyname, contacttitle, phone  <br>
FROM customers  <br>
ORDER BY phone;


#### Create a report that shows the capitalized FirstName and capitalized LastName renamed as FirstName and Lastname  respectively and HireDate FROM the employees table sorted FROM the newest to the oldest employee
SELECT upper(firstname) as FIRST_NAME,  <br>
UPPER(lastname) as LAST_NAME,
hiredate <br>
FROM employees  <br>
ORDER BY hiredate;


#### Create a report that shows the top 10 OrderID, OrderDate, ShippedDate, CustomerID, Freight from the orders table sorted by Freight in descending order
SELECT orderid, orderdate, shippeddate, customerid  <br>
FROM orders <br>
ORDER BY freight DESC <br>
LIMIT 10;


#### Create a report that shows all the CustomerID in lowercase letter and renamed as ID from the customers table
SELECT lower(customerid) as ID <br>
FROM customers;


#### Create a report that shows the CompanyName, Fax, Phone, Country, HomePage from the suppliers table sorted by the Country in descending order then by CompanyName in ascending order
SELECT companyname, fax, phone, country, homepage  <br>
FROM suppliers <br>
order by country DESC, companyname ASC;

SELECT city  <br>
FROM customers;


#### Create a report that shows CompanyName, ContactName of all customers from ‘Buenos Aires' only
SELECT companyname, contactname FROM customers  <br>
where city = 'Buenos Aires'


SELECT unitsinstock  <br>
FROM products;


#### Create a report showing ProductName, UnitPrice, QuantityPerUnit of products that are out of stock
SELECT productname, unitprice, quantityperunit  <br>
FROM products  <br>
where unitsinstock = 0;

SELECT country  <br> FROM customers;


#### Create a report showing all the ContactName, Address, City of all customers not from Germany, Mexico, Spain
SELECT contactname, address, city  <br>
FROM customers <br>
where not country in ('Germany', 'Mexico', 'Spain');

SELECT shippeddate  <br>
FROM orders;


#### Create a report showing OrderDate, ShippedDate, CustomerID, Freight of all orders placed on 21 May 1996.
SELECT orderdate, shippeddate, customerid, freight  <br>
FROM orders  <br>
where shippeddate = '1997-05-21';


#### Create a report showing FirstName, LastName, Country from the employees not from United States.
SELECT firstname, lastname, country  <br>
FROM employees  <br>
WHERE NOT country = 'USA';


#### Create a report that shows the EmployeeID, OrderID, CustomerID, RequiredDate, ShippedDate from all orders shipped later than the required date
SELECT employeeid, orderid, customerid, requireddate, shippeddate <br>
FROM orders <br>
WHERE shippeddate > requireddate;


#### Create a report that shows the City, CompanyName, ContactName of customers from cities starting with A or B
SELECT city, companyname, contactname  <br>
FROM customers <br>
WHERE city LIKE 'A%' OR city LIKE 'B%';

SELECT city  <br>
FROM customers;


#### Create a report showing all the even numbers of OrderID FROM the orders table
SELECT orderid <br>
FROM orders <br>
WHERE mod(orderid,2) = 0;


#### Create a report that shows all the orders where the freight cost more than $500
SELECT * <br>
FROM orders <br>
WHERE freight > '500';


#### Create a report that shows the ProductName, UnitsInStock, UnitsOnOrder, ReorderLevel of all products that are up for reorder.
SELECT productname, unitsinstock, unitsonorder, reorderlevel <br>
FROM products <br>
WHERE discontinued = 0;

SELECT *  <br> FROM products;


#### Create a report that shows the CompanyName, ContactName number of all customer that have no fax number
SELECT companyname, contactname <br>
FROM customers <br>
WHERE fax IS NULL;


#### Create a report that shows the FirstName, LastName of all employees that do not report to anybody
SELECT firstname, lastname <br>
FROM employees <br>
WHERE reportsto IS NULL;

SELECT reportsto  <br>
FROM employees;


#### Create a report showing all the odd numbers of OrderID FROM the orders table
SELECT orderid <br>
FROM orders <br>
WHERE mod(orderid,2) <> 0;


##Create a report that shows the CompanyName, ContactName, Fax of all customers that do not have Fax number and sorted by ContactName
SELECT companyname, contactname <br>
FROM customers <br>
WHERE fax IS NULL <br>
ORDER BY contactname; 


#### Create a report that shows the City, CompanyName, ContactName of customers FROM cities that has letter L in the name sorted by ContactName
SELECT city, companyname, contactname <br>
FROM customers <br>
WHERE city LIKE '%l%' <br>
ORDER BY contactname;


#### Create a report that shows the FirstName, LastName, BirthDate of employees born in the 1950s
SELECT firstname, lastname, birthdate <br>
FROM employees <br>
WHERE birthdate BETWEEN '1950-01-01' and '1959-12-31';

SELECT birthdate <br> FROM employees;


#### Create a report that shows the FirstName, LastName, the year of Birthdate as birth year FROM the employees table
SELECT firstname, lastname, birthdate AS Birth_Year <br>
FROM employees;


#### Create a report showing OrderID, total number of Order ID as NumberofOrders FROM the orderdetails table grouped by 
OrderID and sorted by NumberofOrders in descending order
SELECT orderid, COUNT(orderid) AS numberoforders <br>
FROM order_details <br>
group by orderid <br>
order by numberoforders;


#### Create a report that shows the SupplierID, ProductName, CompanyName FROM all product Supplied by Exotic Liquids, Specialty Biscuits, Ltd., Escargots Nouveaux sorted by the supplier ID
SELECT b.supplierid, a.productname, b.companyname  <br>
FROM products a <br>
JOIN suppliers b <br>
ON a.supplierid = b.supplierid <br>
WHERE companyname in ('Exotic Liquids', 'Specialty Biscuits, Ltd.', 'Escargots Nouveaux') <br>
ORDER by supplierid;
 
 
SELECT companyname  <br>
FROM suppliers;


#### Create a report that shows the ShipPostalCode, OrderID, OrderDate, RequiredDate, ShippedDate, ShipAddress of all orders with ShipPostalCode beginning with "98124"
SELECT shippostalcode, orderid, orderdate, requireddate, shippeddate, shipaddress <br>
FROM orders <br>
WHERE shippostalcode like '98124%';


#### Create a report that shows the ContactName, ContactTitle, CompanyName of customers that the has no "Sales" in their ContactTitle
SELECT contactname, contacttitle, companyname  <br>
FROM customers <br>
where not contacttitle like '%Sales%';

SELECT contacttitle <br> FROM customers;



#### Create a report that shows the LastName, FirstName, City of employees in cities other "Seattle"
SELECT lastname, firstname, city <br>
FROM employees <br>
WHERE city = 'Seattle';



#### Create a report that shows the CompanyName, ContactTitle, City, Country of all customers in any city in Mexico or other  cities in Spain other than Madrid
SELECT companyname, contacttitle, city, country <br>
FROM customers <br>
WHERE country = 'Mexico' OR country = 'Spain' AND city <> 'Madrid';

SELECT city <br> FROM customers;

SELECT * <br> FROM employees;


#### Create a SELECT statement that outputs the following

SELECT CONCAT(firstname,' ',lastname,' ','can be reached at',' ','x',extension) <br>
FROM employees;


#### Create a report that shows the ContactName of all customers that do not have letter A as the second alphabet in their  Contactname
SELECT contactname  <br>
FROM customers <br>
WHERE NOT contactname LIKE '_a%';


#### Create a report that shows the average UnitPrice rounded to the next whole number, total price of UnitsInStock and maximum number of orders FROM the products table. All saved as AveragePrice, TotalStock and MaxOrder respectively
SELECT CEIL(AVG(unitprice)) AS averageprice,  <br>
SUM(unitsinstock) AS totalstock, <br>
MAX(unitsonorder) AS maxorder <br>
FROM products;


#### Create a report that shows the SupplierID, CompanyName, CategoryName, ProductName and UnitPrice FROM the products,  suppliers and categories table
SELECT b.supplierid, b.companyname, c.categoryname, a.productname, a.unitprice <br>
FROM products a <br>
JOIN suppliers b <br>
ON a.supplierid = b.supplierid <br>
JOIN categories c <br>
ON a.categoryid = c.categoryid;


#### Create a report that shows the CustomerID, sum of Freight, FROM the orders table with sum of freight greater $200, grouped by CustomerID
SELECT customerid, SUM(freight) <br>
FROM orders <br>
GROUP BY customerid <br>
HAVING SUM(freight) > 200;


#### Create a report that shows the OrderID ContactName, UnitPrice, Quantity, Discount FROM the order details, orders and customers table with discount given on every purchase
SELECT a.orderid, c.contactname, a.unitprice, a.quantity, a.discount <br>
FROM order_details a <br>
jOIN orders b <br>
ON a.orderid = b.orderid <br>
JOIN customers c <br>
ON b.customerid = c.customerid;

SELECT firstname, reportsto  <br>
FROM employees;


#### Create a report that shows the EmployeeID, the LastName and FirstName as employee, and the LastName and FirstName of who they report to as manager FROM the employees table sorted by Employee
SELECT CONCAT(a.lastname,' ', a.firstname) as employee, <br>
a.employeeid, a.reportsto, <br>
CONCAT(b.lastname,' ', b.firstname) as manager <br>
FROM employees a <br>
JOIN employees b <br>
ON b.employeeid = a.reportsto;


#### Create a report that shows the average, minimum and maximum UnitPrice of all products as AveragePrice, MinimumPrice  and MaximumPrice respectively
SELECT CEIL(AVG(unitprice)) AS averageprice, <br>
CEIL(MIN(unitprice)) AS minimumprice, <br>
CEIL(MAX(unitprice)) AS maximumprice <br>
FROM products;


#### Create a report that shows the average, minimum and maximum UnitPrice of all products as AveragePrice, MinimumPrice 
and MaximumPrice respectively
CREATE VIEW customerinfo AS <br>
SELECT b.companyname, b.contactname, a.customerid, b.contacttitle, b.address,  <br>
b.city, b.country, b.phone, a.orderdate, a.requireddate, a.shippeddate <br>
FROM orders a <br>
JOIN customers b <br>
ON a.customerid = b.customerid;

SELECT * <br> FROM customerinfo;


#### Change the name of the view you created FROM customerinfo to customer details
ALTER VIEW customerinfo <br>
RENAME TO customer_details;

SELECT * <br> FROM customer_details;


#### Create a view named ProductDetails that shows the ProductID, CompanyName, ProductName, CategoryName, Description, QuantityPerUnit, UnitPrice, UnitsInStock, UnitsOnOrder, ReorderLevel, Discontinued FROM the supplier, products and categories tables
CREATE VIEW productdetails AS <br>
SELECT a.companyname, a.contactname, a.contacttitle, b.productid,  <br>
b.productname, c.categoryname, c.description, b.quantityperunit, b.discontinued, <br>
b.unitsinstock, b.unitsonorder, b.reorderlevel <br>
FROM suppliers a <br>
JOIN products b <br>
ON a.supplierid = b.supplierid <br>
JOIN categories c <br>
ON b.categoryid = c.categoryid;


#### Drop the customer details view
DROP VIEW customer_details;

SELECT * <br> FROM productdetails;


#### Create a report that fetch the first 5 character of categoryName FROM the category tables and renamed as ShortInfo
SELECT SUBSTRING(categoryname, 1, 5) AS shortinfo <br>
FROM categories;


#### Create a copy of the shipper table as shippers_duplicate. Then insert a copy of shippers data into the new table
CREATE TABLE shipper_duplicate AS <br>
SELECT * FROM shippers;

SELECT * <br> FROM shipper_duplicate;


CREATE TABLE test (LIKE shippers);

INSERT INTO test
SELECT * <br>
FROM shippers;

SELECT * <br>
FROM test


#### Create a SELECT statement that outputs the following FROM the shippers_duplicate Table
SELECT shipperid, companyname, phone, <br>
CONCAT(REPLACE(LOWER(companyname),' ',''),'@gmail.com') AS email <br>
FROM shippers  <br>
ORDER BY shipperid <br>
LIMIT 3;

SELECT * <br> FROM categories;


#### Create a report that shows the CompanyName and ProductName FROM all product in the Seafood category
SELECT a.companyname, b.productname  <br>
FROM suppliers a <br>
JOIN products b <br>
ON a.supplierid = b.supplierid <br>
JOIN categories c <br>
ON b.categoryid = c.categoryid <br>
where c.categoryname = 'Seafood';


#### Create a report that shows the CategoryID, CompanyName and ProductName FROM all product in the categoryID 5
SELECT c.categoryid, a.companyname, b.productname <br>
FROM suppliers a <br>
JOIN products b <br>
ON a.supplierid = b.supplierid <br>
JOIN categories c <br>
ON b.categoryid = c.categoryid <br>
WHERE c.categoryid = 5;


#### Delete the shippers_duplicate table
DROP TABLE shipper_duplicate;


#### Create a SELECT statement that ouputs the following FROM the employees table. <br>
NB: The age might differ depending on the year you are attempting this query##
SELECT lastname, firstname, title, <br>
AGE(CURRENT_DATE, birthdate) <br>
FROM employees;


#### Create a report that the CompanyName and total number of orders by customer renamed as number of orders since Decemeber 31, 1994. Show number of Orders greater than 10

CREATE TABLE no_of_orders AS <br>
SELECT d.companyname, c.unitsonorder <br>
FROM order_details a  <br>
JOIN orders b  <br>
ON b.orderid = a.orderid <br>
JOIN products c <br>
ON a.productid = c.productid <br>
JOIN customers d <br>
ON b.customerid = d.customerid <br>
WHERE unitsonorder > 10; <br>

SELECT * <br> FROM no_of_orders; 

SELECT * <br> FROM products;


#### Create a SELECT statement that ouputs the following FROM the product table <br>
NB: It should return 77rows
SELECT CONCAT(productname, ' ', 'weighs/is', ' ', quantityperunit, ' ', 'and',' ', 'cost', ' ', '$',unitprice) <br>
FROM products;
