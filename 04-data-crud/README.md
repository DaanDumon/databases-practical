# Data CRUD

Author: Daan Dumon

Write queries for example data. Choose **your own subject**. Write queries for the following actions:

* Creation of a database
* Usage of that new database
* Create a table (choose the correct datatypes for the different columns) with minimum 4 columns
* Insert a single row of data in the table
* Insert minimum 5 rows of data in the table (using a single query command)
* Add an extra attribute (column) to your table
* Show all column names with there properties (column names, datatype,...)
* Update minimum 1 row where you insert a new value to the newly created column
* Delete a row from your table
* Show all data from the table

If you have no idea's about the subject, you could create your database around: cars, plants, computers, graphics cards, microcontrollers, invoices, students, exams, ...

## Create database query

Give a query that creates a new database. Choose your own subject, and choose a meaningful corresponding name for your database.

```sql
  use exercise_o4;

```

## Use database query

Give a query that will set the default database to your newly created database. This way, future queries will be run in the context of that database.

```sql
 USE exercise_04;

```

## Create table query

Give a query that will create a new table that you will use to manage some data covering your chosen subject. Choose a meaningful name for this table.
Provide minimum 4 columns for your table. Make sure to choose the correct datatypes for the different properties.

Add an extra row that is called `id` that will be set as *primary key*, and will be *auto incremented*.

```sql
  MariaDB [exercise_04]>  Create table operators(
    -> ash TINYTEXT,
    -> thermite TINYTEXT,
    -> sledge TINYTEXT,
    -> doc TINYTEXT,
    -> id INT AUTO_INCREMENT,
    -> PRIMARY KEY(id));
Query OK, 0 rows affected (0.023 sec)

```

## Insert a single row

Give a query that wil insert a single row into your newly create table. Pick some realistic data, try not to insert some nonsense. Do not insert the `id` attribute manually, but let the database decide a value.

```sql
  MariaDB [exercise_04]> insert into operators(
    -> ash,
    -> thermite,
    -> sledge,
    -> doc,
    -> id)
    -> values (
    -> '3 speed',
    -> '2 speed',
    -> '2 speed',
    -> '1 speed',
    -> NULL);
Query OK, 1 row affected (0.002 sec)
  
 

```

## Insert multiple rows at once

Give a query that will insert multiple rows at once. Only provide a single query that inserts minimum 5 rows. Again do not provide an `id` attribute yourself.

```sql
  MariaDB [exercise_04]> INSERT INTO operators (
    -> ash,
    -> thermite,
    -> sledge,
    -> doc,
    -> id)
    -> VALUES(
    -> '1 armour',
    -> '2 armour',
    -> '2 armour',
    -> '3 armour',
    -> NULL
    -> ),(
    -> 'Female',
    -> 'male',
    -> 'male',
    -> 'male',
    -> NULL
    -> ),(
    -> 'redhead',
    -> 'brown hair',
    -> 'bald',
    -> 'black hair',
    -> NULL
    -> ),(
    -> 'Breaching round',
    -> 'sledgehammer',
    -> 'exothermic charges',
    -> 'stim pistols',
    -> NULL
    -> ),(
    -> 'flash nades',
    -> 'flash nades',
    -> 'frag nades',
    -> 'barbed wire',
    -> NULL);
Query OK, 5 rows affected (0.003 sec)
Records: 5  Duplicates: 0  Warnings: 0

```

## Add an extra column to the table

Choose an extra attribute to add to the table. Give a query that will make this change to your table.

```sql
  MariaDB [exercise_04]> ALTER TABLE operators
    -> ADD release_date datetime;
Query OK, 0 rows affected (0.008 sec)
Records: 0  Duplicates: 0  Warnings: 0

```

## Show all the columns and their properties

Give a query that will show all column names with there properties (column names, datatype,...). Copy paste the result from powershell in your answer as well.

```sql
  MariaDB [exercise_04]> SELECT * FROM operators;
```

Result:

```text
  +-----------------+--------------+--------------------+--------------+----+--------------+
| ash             | thermite     | sledge             | doc          | id | release_date |
+-----------------+--------------+--------------------+--------------+----+--------------+
| 3 speed         | 2 speed      | 2 speed            | 1 speed      |  1 | NULL         |
| 1 armour        | 2 armour     | 2 armour           | 3 armour     |  2 | NULL         |
| Female          | male         | male               | male         |  3 | NULL         |
| redhead         | brown hair   | bald               | black hair   |  4 | NULL         |
| Breaching round | sledgehammer | exothermic charges | stim pistols |  5 | NULL         |
| flash nades     | flash nades  | frag nades         | barbed wire  |  6 | NULL         |
+-----------------+--------------+--------------------+--------------+----+--------------+
6 rows in set (0.000 sec)

```

## Updating existing rows

Give a query that will update minimum 1 row where you insert a new value to the newly created column.

```sql
  MariaDB [exercise_04]> UPDATE operators
    -> SET
    -> release_date = 1;
Query OK, 6 rows affected, 6 warnings (0.002 sec)
Rows matched: 6  Changed: 6  Warnings: 6
```

## Delete a row from your table

Choose a row (one that you did not update in previous question) and give a query that will delete that single row.

```sql
  MariaDB [exercise_04]> ALTER TABLE operators
    -> DROP COLUMN thermite;
Query OK, 0 rows affected (0.008 sec)
Records: 0  Duplicates: 0  Warnings: 0

```

## Show all data from the table

Give a query that will show your entire table with all the columns and all its data. It's important that the data will reflect all previous executed queries. Copy paste the result from powershell in your answer as well.

```sql
  MariaDB [exercise_04]> SELECT * FROM operators;
```

Result:

```text
  +-----------------+--------------------+--------------+----+---------------------+
| ash             | sledge             | doc          | id | release_date        |
+-----------------+--------------------+--------------+----+---------------------+
| 3 speed         | 2 speed            | 1 speed      |  1 | 0000-00-00 00:00:00 |
| 1 armour        | 2 armour           | 3 armour     |  2 | 0000-00-00 00:00:00 |
| Female          | male               | male         |  3 | 0000-00-00 00:00:00 |
| redhead         | bald               | black hair   |  4 | 0000-00-00 00:00:00 |
| Breaching round | exothermic charges | stim pistols |  5 | 0000-00-00 00:00:00 |
| flash nades     | frag nades         | barbed wire  |  6 | 0000-00-00 00:00:00 |
+-----------------+--------------------+--------------+----+---------------------+
6 rows in set (0.000 sec)

```

## Report

When you are ready and submitted the exercise, make sure to fill in the [report](./REPORT.md) file. Don't forget to commit it as well. Answer all questions and check the formatting by viewing the file on GitHub.
