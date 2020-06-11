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

