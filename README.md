# SQLAssignment

# Plz refer to sampleERdiagram.jpg to get the idea of Schema. 

#Questions

1.      List the customer name, check number, payment date and amount for the customer with customer number 1001.


2.      List the employee number, last name and first name for all the employees  who reports to their manager with employee id 1001.


3.      List the customer name, phone and total amount of all customers with credit limit greater than 10000.


4.      List all the order number, order date, product code, product name, quantity ordered, price each  for the customer with customer number 1001.

#Answers

1. select customers.customerNumber,checkNumber,paymentDate,amount from customers INNER JOIN payments ON customers.customerNumber=payments.customerNumber where customers.customerNumber=1001;

2. select e.employeeNumber,e.lastName,e.firstName From employees e,employees m WHERE e.reportsTO=m.employeeNumber AND       e.reportsTo=1001;

3. select customerName,phone,sum(amount) AS sum From customers, payments WHERE customers.customerNember=payments.customerNumber AND creditLimit>10000;

4. select OD.orderNumber,OD.orderDate,productCode,quantityOrdered,price from (orders  INNER JOIN orderdetails AS OD ON orders.orderNumber=orderdetails.orderNumber) where customers.customerNumber=1001;
