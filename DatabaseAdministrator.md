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

