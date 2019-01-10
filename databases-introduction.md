#### Questions

> What data types do each of these values represent?

- "A Clockwork Orange"
  string

- 42
  integer

- 09/02/1945
  date

- 98.7
  float

- \$15.99
  money (depends what flavor of sql. could be a float with a currency identifier stored elsewhere, or it could just be a string)

> Explain when a database would be used. Explain when a text file would be used.

- Database - used when you need persistent data that may be updated by multiple programs/sessions simultaneously, if you are storing a lot of data, and/or if the relationships between the different pieces of data are important (Relational DBs).

- text file - persistent data that only needs to be read, or only updated by one program at a time. smaller amounts of data. typically less complicated data, or data where the relationships between the individual pieces of data aren't very important.

> Describe one difference between SQL and other programming languages.
> there isn't an assignment operator, so "=" is used for equality, similar to "==" in most other programming languages.
> SQL is also declarative, so you are describing what you want the DB to do for you, rather than the exact steps the DB should take(imperative/procedural programming)

> In your own words, explain how the pieces of a database system fit together at a high level.
> Databases are made up of tables, related to one another by keys.
> Tables represent collections of data. Each table has a series of columns. Each column describes the meaning of a piece of data in the table. Each row in the table is a set of data which contains values in one or more of the columns of that table. Each piece of data in the row might be readable data, or it might be a key, referring to a row in a different table.

> Explain the meaning of table, row, column, and value.
> See above

> List three data types that can be used in a table

- text/string
- date
- integer

> Given this`payments` table, provide an English description of the following queries and include their results:

```sql
SELECT date, amount
FROM payments
```

Description: give me the date and amount for every payment

Results:

| date                     | amount    |
| ------------------------ | --------- |
| 2016-05-01T00:00:00.000Z | 1500.0000 |
| 2016-05-10T00:00:00.000Z | 37.0000   |
| 2016-05-15T00:00:00.000Z | 124.9300  |
| 2016-05-23T00:00:00.000Z | 54.7200   |

```sql
SELECT amount
FROM payments
WHERE amount > 500;
```

Description: give me the amounts of all payments over 500

Results:
| amount |
| --------- |
| 1500.0000 |

```sql
SELECT *
FROM payments
WHERE payee = 'Mega Foods';
```

Description: give me every piece of information in the payments table about payments made to Mega Foods

Results:

| date                     | payee      | amount   | memo      |
| ------------------------ | ---------- | -------- | --------- |
| 2016-05-15T00:00:00.000Z | Mega Foods | 124.9300 | Groceries |

> Given this users table, write SQL queries using the following criteria and include the output:

- The email and sign-up date for the user named DeAndre Data.

```sql
SELECT email, signup
FROM users
WHERE name='DeAndre Data';
```

Output:

| email             | signup                   |
| ----------------- | ------------------------ |
| datad@comcast.net | 2008-01-20T00:00:00.000Z |

- The user ID for the user with email 'aleesia.algorithm@uw.edu'.

```sql
SELECT userid
FROM users
WHERE email='aleesia.algorithm@uw.edu';
```

Output:

| userid |
| ------ |
| 1      |

- All the columns for the user ID equal to 4.

```sql
SELECT *
FROM users
WHERE userid='4'
```

Output:

| userid | name           | email             | signup                   |
| ------ | -------------- | ----------------- | ------------------------ |
| 4      | Brandy Boolean | bboolean@nasa.gov | 1999-10-15T00:00:00.000Z |
