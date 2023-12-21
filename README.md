# SQL-_Portfolio
A collection of my sample SQL script. Written from a MUSIC File database in SQL Esseential Training course

Ex 1. 
/* Pull Names and Emails 
*/

SELECT
 FirstName,
 LastName,
 Email
FROM
 Customer

EX 2 
/*Specify column names
*/
SELECT
 FirstName AS[Customer First Name],
 LastName AS[Customer Last Name],
 Email AS EMAIL
FROM
 Customer
*/

Ex 3. 
/* ASC & DESC 
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
/* Points to brussels as billing city 
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
 /*Date and total $ less then 3.00
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
/*Create a Mailing List of US Customers
*/ String Function - using Length to show zip codes

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
/*Calculate the ages of all employees
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
Nesting function using Round
*/

SELECT
    SUM(Total) AS [Total Sales],
round(AVG(Total),2) AS [Average Sales],
    MAX(Total) AS [Maximum Sales],
    MIN(Total) AS [Minimum Sales],
    COUNT(*) AS [Sales COUNT]
FROM
    Invoice

