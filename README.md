# Practice: SQL Subqueries

In this project, you will be executing SQL commands with at least one subquery.

## Set up

`cd` into the __sql-practice__ folder.

Run `npm install` to install the dependencies.

Execute the file __build-db.sql__ in the terminal to build the database, 
and populate it with seed data.

```shell
sqlite3 db.sqlite ".read build-db.sql"
```

In the _sql-practice_ folder, create a file called _subqueries.sql_ to hold your
work. Run the file on the created database to complete the phases below.

## Prepare

The tables are structured as follows...

`cats` Table:

| column     | type    | constraints |
| ---------- | ------- | ----------- |
| id         | INTEGER | PRIMARY KEY |
| name       | TEXT    |             |
| birth_year | INTEGER |             |

`toys` Table:

| column | type    | constraints                     |
| ------ | ------- | ------------------------------- |
| id     | INTEGER | PRIMARY KEY                     |
| name   | TEXT    |                                 |
| cat_id | INTEGER | FOREIGN KEY REFERENCES cats(id) |

Run a few queries using the command line (CLI) to see the `cats` and `toys` 
provided in the seed data. 

Use a `JOIN` query to explore their relationship.

Exit the `sqlite3` command line.

## Phase 1: Replace `JOIN` query with subquery

Write a JOIN query to get the list of toys belonging to Garfield.

Rewrite the JOIN query using a subquery instead.

## Phase 2: Dynamic `INSERT` using subquery

Give Garfield a new toy named "Pepperoni" using a subquery for Garfield's id.

Verify the insertion worked using one of the queries above.

> Tip #1: If you place the `INSERT` between the `JOIN` query and the subquery,
> you'll "automatically" have before-and-after testing.

> Tip #2: You can write additional text to the screen using `SELECT` to return
> a constant. (Research this online if you're not sure how to do it.)

> Tip #3: You can put multiple `.read` commands in the same shell command for 
> faster testing (e.g. rebuild from seed data followed by subqueries).

```shell
sqlite3 db.sqlite ".read build-db.sql" ".read subqueries.sql"
```