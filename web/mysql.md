# MySQL

1. Relational database management system.
2. Open-source.
3. Free.
4. Great for small or large applications.
5. Fast, reliable, scalable, and easy to use.
6. Cross-platform.

## Comparison to PostgreSQL

| Feature | MySQL | PostgreSQL |
|---|---|---|
| Data types | Supports basic data types such as numeric, character, date and time, spatial, and JSON | Supports all MySQL data types along with geometric, enumerated, network address, arrays, ranges, XML, hstore, and composite |
| Features | Limited support for database features such as views, triggers, and procedures | Supports most advanced database features such as materialized views, INSTEAD OF triggers, and stored procedures in multiple languages |
| Scalability | Can handle large datasets, but may not be as scalable as PostgreSQL | Can handle very large datasets and is well-suited for high-traffic applications |
| Concurrency | Can handle multiple concurrent users, but may not be as efficient as PostgreSQL | Can handle many concurrent users and is very efficient |
| Data integrity | Supports ACID (atomicity, consistency, isolation, durability) transactions | Supports ACID transactions and has additional features for data integrity such as foreign keys and triggers |
| Licensing | GPLv2 | PostgreSQL License |

## RDBMS

RDBMS stands for relational database management system used to maintain relational database. It's the basis for all modern database systems such as MySQL, Oracle etc, and makes use of SQL queries to access the data in the database.

## Queries

1. SELECT

```sql
	SELECT Name, Age, City FROM Customers
	WHERE City = 'Berlin' AND Age > 20 AND Age < 30;
```

2. UPDATE
3. DELETE
4. INSERT INTO
5. CREATE DATABASE
6. ALTER DATABASE
7. CREATE TABLE
8. DROP TABLE
9. CREATE INDEX
10 DROP INDEX