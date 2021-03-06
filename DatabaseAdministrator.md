## Roles

### Create Role

```sql
CREATE ROLE maudy LOGIN PASSWORD 'ayunda' VALID UNTIL 'infinity' CREATEDB;
```

### Create Superuser

```sql
CREATE ROLE febrianza LOGIN PASSWORD 'gungun' VALID UNTIL '2020-1-1 00:00'
SUPERUSER;
```

### Create Group Roles

```sql
CREATE ROLE MojangIndonesia INHERIT;
```

### Add Member to Group

```sql
GRANT royalty TO maudy;
```

-------------

## Select

### Select All Rows & Columns

```sql
SELECT * FROM customers
```

### Select Partial Columns

```sql
SELECT name, address, company FROM customers
```

### Select Column By Alias

```sql
SELECT name AS "username", address AS "from", company AS "Occupation" FROM customers
```

```sql
SELECT x.name, x.address, x.company FROM customers AS x
```

```sql
SELECT x.name AS "username", x.address AS "from", x.company AS "Occupation" FROM customers AS x
```

### Select Literal

```sql
SELECT 'My order Num is :' as "user_column1",
        ORDER_ID ,
		'Quantity Sold is:' as "user_column2",
		QUANTITY ,
		0.2 as "Commision" 
FROM order_details;
```

### Select Column Operation

```sql
SELECT ORDER_ID, QUANTITY, UNIT_PRICE, UNIT_PRICE * 2 AS "New Unit Price" FROM ORDER_DETAILS
```

### Select Column Concat 

```sql
SELECT 'User Order ' || ORDER_ID || ' - ' || UNIT_PRICE AS "Data", UNIT_PRICE * 2 AS "New Unit Price" FROM ORDER_DETAILS
```

### Where Clause

```sql
SELECT * FROM Customers WHERE last_name = 'Lee'
```

### Where Clause - And Operator

```sql
SELECT * FROM employees WHERE job_title = 'Sales Representative' AND city = 'Seattle'
```

### Where Clause - Or Operator

```sql
SELECT * FROM employees WHERE job_title = 'Sales Representative' OR city = 'Seattle'
```

### Where Clause - Like Operator

```sql
SELECT * FROM products WHERE category LIKE 'D%'
```

```sql
SELECT * FROM products WHERE category LIKE '%s'
```

```sql
SELECT * FROM products WHERE category LIKE '%Dried%'
```

```sql
SELECT * FROM products WHERE category LIKE '_____@%'
```

### Where Clause - Between Operator

```sql
SELECT ID, SHIPPING_FEE FROM ORDERS WHERE SHIPPING_FEE BETWEEN 100 AND 200
```

```sql
SELECT ID, SHIPPING_FEE FROM ORDERS WHERE SHIPPING_FEE NOT BETWEEN 100 AND 200
```

```sql
SELECT ID, SHIP_CITY FROM ORDERS WHERE SHIP_CITY BETWEEN 'A' AND 'B'
```

```sql
SELECT ID, ORDER_DATE FROM ORDERS WHERE ORDER_DATE BETWEEN '2006-01-01' AND '2006-03-31'
```

### Where Clause - In Operator

```sql
SELECT ID, SHIPPER_ID FROM ORDERS WHERE SHIPPER_ID = 1 OR SHIPPER_ID = 2
```

Another Good way :

```sql
SELECT ID, SHIPPER_ID FROM ORDERS WHERE SHIPPER_ID IN (1,2)
```

### Where Clause - Not In Operator

```sql
SELECT ID, SHIPPER_ID FROM ORDERS WHERE SHIPPER_ID NOT IN (1,2)
```

```sql
SELECT ID, PAYMENT_TYPE FROM ORDERS WHERE PAYMENT_TYPE NOT IN ('Cash','Check')
```

### Where Clause - Comparison Operator

```sql
SELECT * FROM EMPLOYEES WHERE FIRST_NAME != 'Maudy Ayunda'
```

```sql
SELECT * FROM ORDERS WHERE ID > 30
```

```sql
SELECT * FROM ORDERS WHERE ID >= 30
```

### Limit Operator

```sql
SELECT * FROM EMPLOYEES LIMIT 5
```

```sql
SELECT * FROM EMPLOYEES LIMIT 5 OFFSET 3
```

### Distinct Clause

```sql
SELECT DISTINCT SHIPPER_ID, SHIP_CITY FROM ORDERS
```

```sql
SELECT DISTINCT EMPLOYEE_ID FROM orders;
```

### Order By

```sql
SELECT SHIPPER_ID, SHIP_CITY FROM ORDERS ORDER BY SHIPPER_ID ASC
```

```sql
SELECT SHIPPER_ID, SHIP_CITY FROM ORDERS ORDER BY SHIPPER_ID DESC
```

```sql
SELECT SHIPPER_ID, SHIP_CITY FROM ORDERS ORDER BY SHIPPER_ID ASC, SHIP_CIDY DESC
```

### Order By - Move Null

```sql
SELECT SHIPPER_ID, SHIP_CITY FROM ORDERS ORDER BY SHIPPER_ID DESC NULLS LAST
```

```sql
SELECT SHIPPER_ID, SHIP_CITY FROM ORDERS ORDER BY SHIPPER_ID DESC NULLS FIRST
```

### Null Handling

```sql
SELECT ID, PAYMENT_TYPE FROM ORDERS WHERE PAYMENT_TYPE IS NULL
```

```sql
SELECT ID, PAYMENT_TYPE FROM ORDERS WHERE PAYMENT_TYPE IS NOT NULL
```

