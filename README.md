# SQL-_Portfolio
A collection of my sample SQL script. These were scripts written for an online Training class in SQL. Each script has a descriptive note. 


Written from a MUSIC File database in SQL Esseential Training course

Ex 1. 
/* A list of records from the Customer table, with each record containing the values for FirstName, LastName, and Email for a particular customer.
*/

SELECT
 FirstName,
 LastName,
 Email
FROM
 Customer


EX 2 
/*This shows 3 columns: "Customer First Name," "Customer Last Name," and "EMAIL," containing the corresponding values from the "Customer" table. The use of aliases makes the output more readable and provides more meaningful column names.
*/


SELECT
 FirstName AS[Customer First Name],
 LastName AS[Customer Last Name],
 Email AS EMAIL
FROM
 Customer
*/


Ex 3. 
/* This is a list of records from the "Customer" table, sorted first by "Customer First Name" in ascending order and then within each group by "Customer Last Name" in descending order.
*/


SELECT
 FirstName AS[Customer First Name],
 LastName AS[Customer Last Name],
 Email AS EMAIL
FROM
 Customer
 ORDER BY
  FirstName ASC,
  LastName DESC
*/


ex 4. 
/* list of records from the "Invoice" table, including columns for invoice date, billing address, billing city, and total, but only for invoices where the billing city is 'Brussels'. 
*/

SELECT
InvoiceDate,
BillingAddress,
BillingCity,
total
FROM
Invoice
WHERE
BillingCity ='Brussels'
 ORDER BY
 InvoiceDate



 EX 5. - 
 /*list of records from the "Invoice" table, including columns for invoice date, billing address, billing city, and total, but only for invoices where the invoice date is after '2010-05-22' and the total is less than 3.00. 
*/
SELECT
InvoiceDate,
BillingAddress,
BillingCity,
total
FROM
Invoice
WHERE
 date(INVOICEDATE) >'2010-05-22' AND TOTAL < 3.00
 ORDER BY
 InvoiceDate


Ex 6. 
/* list of records from the "Customer" table for customers in the USA. It includes columns for first name, last name, address, a concatenated mailing address, and the length of the postal code for each customer.
*/ 

SELECT
FirstName,
LastName,
Address,
FirstName ||' '|| LastName||''|| Address || ','|| City || State|| ','|| PostalCode AS [Mailing Address],
length(postalcode)
FROM
Customer
WHERE
Country = 'USA'



eX 7. 
/*list of records from the "Employee" table with columns for last name, first name, birthdate, birthdate without the time component, and the age of each employee in days.
*/

SELECT
Lastname,
FirstName,
BirthDate,
strftime('%Y-%m_%d',Birthdate) as [BirthDate No Timecode],
strftime('%Y-%m-%d','now')-strftime('%Y-%m-%d',Birthdate) AS Age
FROM
Employee

/*
Total global sales of all time
*/

SELECT
    SUM(Total) AS [Total Sales],
    AVG(Total) AS [Average Sales],
    MAX(Total) AS [Maximum Sales],
    MIN(Total) AS [Minimum Sales],
    COUNT(*) AS [Sales COUNT]
FROM
    Invoice



Ex 8. 
/*
single row with aggregate information about the "Total" column in the "Invoice" table, including total sales, average sales, maximum sales, minimum sales, and the count of sales.
*/

SELECT
    SUM(Total) AS [Total Sales],
round(AVG(Total),2) AS [Average Sales],
    MAX(Total) AS [Maximum Sales],
    MIN(Total) AS [Minimum Sales],
    COUNT(*) AS [Sales COUNT]
FROM
    Invoice

