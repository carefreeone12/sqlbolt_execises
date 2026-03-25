# SQL Lesson 4: Filtering and sorting Query results
To manage large datasets and ensure query results are readable, SQL provides clauses to filter duplicates, sort data, and restrict the output size. The `DISTINCT` keyword immediately removes duplicate rows from the result set based on the selected columns. The `ORDER` BY clause sorts the output alphanumerically by specified columns in ascending (`ASC`) or descending (`DESC`) order, which is crucial since databases do not inherently store rows in a sorted sequence. Finally, the `LIMIT` and optional `OFFSET` clauses optimize performance by restricting the number of returned rows and defining a starting point, a technique commonly used for pagination in scalable applications.

## Exercise:
The exercises in this lesson apply the newly introduced clauses to a randomized **Movies** table, simulating real-world unstructured data environments. Apply the necessary sorting and filtering keywords to structure the results.

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 4 | Monsters, Inc. | Pete Docter | 2001 | 92 |
| 5 | Finding Nemo | Andrew Stanton | 2003 | 107 |
| 6 | The Incredibles | Brad Bird | 2004 | 116 |
| 7 | Cars | John Lasseter | 2006 | 117 |
| 8 | Ratatouille | Brad Bird | 2007 | 115 |
| 9 | WALL-E | Andrew Stanton | 2008 | 104 |
| 10 | Up | Pete Docter | 2009 | 101 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |
| 12 | Cars 2 | John Lasseter | 2011 | 120 |
| 13 | Brave | Brenda Chapman | 2012 | 102 |
| 14 | Monsters University | Dan Scanlon | 2013 | 110 |

## Solution:

**Question-1:** *List all directors of Pixar movies (alphabetically), without duplicates.*

**Query:** `SELECT DISTINCT(director) FROM movies ORDER BY 1 ASC;`

**Output:**

| director |
|---|
| Andrew Stanton |
| Brad Bird |
| Brenda Chapman |
| Dan Scanlon |
| John Lasseter |
| Lee Unkrich |
| Pete Docter |

**Question-2:** *List the last four Pixar movies released (ordered from most recent to least).*

**Query:** `SELECT title, year FROM movies ORDER BY 2 DESC LIMIT 4;`

**Output:**

| title | year |
|---|---|
| Monsters University | 2013 |
| Brave | 2012 |
| Cars 2 | 2011 |
| Toy Story 3 | 2010 |

**Question-3:** *List the first five Pixar movies sorted alphabetically.*

**Query:** `SELECT title FROM movies ORDER BY 1 ASC LIMIT 5;`

**Output:**

| title |
|---|
| A Bug's Life |
| Brave |
| Cars |
| Cars 2 |
| Finding Nemo |

**Question-4:** *List the next five Pixar movies sorted alphabetically.*

**Query:** `SELECT title FROM movies ORDER BY 1 ASC LIMIT 5 OFFSET 5;`

**Output:**

| title |
|---|
| Monsters University |
| Monsters, Inc. |
| Ratatouille |
| The Incredibles |
| Toy Story |