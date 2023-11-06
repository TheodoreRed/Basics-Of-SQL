# Basic SQL Study Guide

## Understanding Tables and Records

In SQL, information is stored in structures called tables. Here's an example of how to retrieve data from a table:

```sql
SELECT column1, column2 FROM tableName;
```

- `tableName` is the name of the table in your database.
- `column1` and `column2` are the names of the columns in the `tableName` table.

Executing the above query will return a result set consisting of data from the specified columns for each row in the `tableName` table. The result will appear in the form of a table with the number of columns you have specified in the query.

## Sample Table: Users

Consider a table named `users` with columns `username` and `email`.

```sql
SELECT username, email FROM users;
```

- `users` is the name of the table.
- `username` and `email` are column names within the `users` table.

The result of this query will give you a list of usernames and their corresponding email addresses.

Example output:

```
+------------+---------------------+
| username   | email               |
+------------+---------------------+
| johndoe    | john@example.com    |
| janedoe    | jane@example.com    |
| bobjohnson | bob@example.com     |
| ...        | ...                 |
+------------+---------------------+
```

Each row in the output represents a record from the `users` table showing the `username` and `email`.

## Filtering Data

To filter data, we use the `WHERE` clause:

```sql
SELECT column1, column2 FROM tableName WHERE condition;
```

- The `condition` specifies which rows to retrieve.

For example, to get users who registered after a certain date:

```sql
SELECT username, email FROM users WHERE registration_date > '2023-01-01';
```

This query fetches usernames and emails of users who registered after January 1, 2023.

## Sorting Data

Sorting data is done with the `ORDER BY` clause:

```sql
SELECT column1, column2 FROM tableName ORDER BY column1;
```

- It orders the output based on the specified column.

If you want to see the oldest users in your database first:

```sql
SELECT username, email FROM users ORDER BY registration_date ASC;
```

The `ASC` keyword means ascending order. Use `DESC` for descending order.

## Combining Filters and Sorting

You can combine `WHERE` and `ORDER BY`:

```sql
SELECT username, email FROM users WHERE active = 1 ORDER BY registration_date DESC;
```

This will display active users sorted by their registration date, with the most recent first.

## Aggregating Data

SQL can perform calculations on data, such as counting records:

```sql
SELECT COUNT(*) FROM tableName;
```

- `COUNT(*)` counts all rows in the `tableName`.

To count all registered users:

```sql
SELECT COUNT(*) FROM users;
```

You can also count conditionally:

```sql
SELECT COUNT(*) FROM users WHERE active = 1;
```

This counts only active users.

## Summary

This guide provides a foundational understanding of SQL:

- Use `SELECT` to choose which columns of data you want.
- Use `WHERE` to filter data based on conditions.
- Use `ORDER BY` to sort the data.
- Aggregate functions like `COUNT()` help summarize data.

Practice with these basic commands to build a strong foundation in SQL.
