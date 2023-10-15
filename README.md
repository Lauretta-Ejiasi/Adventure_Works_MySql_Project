# MySql-Projects
**Adventure Works SQL Project**

Q1 - Prepare a list of offices sorted by country, state, city. 
Ans: SELECT COUNTRY, STATE, CITY FROM OFFICES ORDER BY COUNTRY, STATE, CITY ASC;

Q2 - How many employees are there in the company? 
Ans: SELECT COUNT(EMPLOYEENUMBER) FROM EMPLOYEES;

Q3 - What is the total of payments received? 
Ans: SELECT SUM(AMOUNT) AS TOTAL_AMOUNTS FROM PAYMENTS;

Q4 - List the product lines that contain 'Cars' 
Ans: SELECT * FROM PRODUCTLINES WHERE PRODUCTLINE LIKE '%Cars';

Q5 - Report total payments for October 28, 2004 
Ans: SELECT PAYMENTDATE, SUM(AMOUNT) FROM PAYMENTS WHERE PAYMENTDATE = '2004-10-28';

Q6 - Report those payments greater than \\$100,000. 
Ans: SELECT AMOUNT FROM PAYMENTS WHERE AMOUNT > 100000;

Q7 - List the products in each product line 
Ans: SELECT DISTINCT PRODUCTLINE FROM PRODUCTS;

Q8 - How many products in each product line?
Ans: SELECT COUNT(DISTINCT PRODUCTNAME) AS NO_OF_PRODUCTS, PRODUCTLINE FROM PRODUCTS GROUP BY PRODUCTLINE;

Q9 - What is the minimum payment received? 
Ans: SELECT * FROM PAYMENTS ORDER BY AMOUNT ASC;

Q10 - List all payments greater than twice the average payment. 
Ans: SELECT * FROM PAYMENTS WHERE AMOUNT >2* (SELECT AVG(AMOUNT) FROM PAYMENTS);

Q11 - What is the average percentage markup of the MSRP on buyPrice? 
Ans: SELECT BUYPRICE, AVG(MSRP) AS AVG_MSRP_ON_BUYPRICE FROM PRODUCTS GROUP BY BUYPRICE;

Q12 - How many distinct products does ClassicModels sell? 
Ans: SELECT DISTINCT PRODUCTNAME, COUNT(PRODUCTLINE) FROM PRODUCTS GROUP BY PRODUCTNAME;

Q13 - Report the name and city of customers who don't have sales representatives. 
Ans: SELECT CUSTOMERNAME, CITY, SALESREPEMPLOYEENUMBER FROM CUSTOMERS WHERE SALESREPEMPLOYEENUMBER IS NULL;

Q14 - What are the names of executives with VP or Manager in their title? Use the CONCAT function to combine the employees first name and last name into a single field for reporting. 
Ans: SELECT CONCAT (LASTNAME, ' ' , FIRSTNAME) AS EMPLOYEE_NAME, JOBTITLE FROM EMPLOYEES WHERE JOBTITLE LIKE '%VP%' OR JOBTITLE LIKE '%MANAGER%';

Q15 - Which orders have a value greater than $5000?
Ans: SELECT PAYMENTS.AMOUNT, PAYMENTS.CUSTOMERNUMBER, PAYMENTS.PAYMENTDATE FROM PAYMENTS INNER JOIN ORDERS ON ORDERS.CUSTOMERNUMBER=PAYMENTS.CUSTOMERNUMBER WHERE AMOUNT > 5000 ORDER BY AMOUNT ASC
