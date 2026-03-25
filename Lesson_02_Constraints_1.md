# SQL Lesson 2: Queries with constraints (Pt. 1)
The `WHERE` clause optimizes data retrieval by filtering specific rows based on defined conditions, significantly improving query performance on large datasets. Complex filters can be constructed using logical keywords (`AND`, `OR`) combined with numerical operators such as standard inequalities, `BETWEEN`, and `IN`. Constraining the returned rows ensures that the resulting dataset is both manageable and relevant. Additionally, capitalizing standard SQL keywords is a best-practice convention that clearly distinguishes them from table and column names, greatly enhancing query readability.

## Exercise:
Using the right constraints, find the information we need from the Movies table for each task below.

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

**Question-1:** *Find the movie with a row id of 6.*

**Query:** `SELECT title FROM movies WHERE id = 6;`

**Output:**

| title |
|---|
| The Incredibles |

**Question-2:** *Find the movies released in the years between 2000 and 2010.*

**Query:** `SELECT title FROM movies WHERE year BETWEEN 2000 AND 2010;`

**Output:**

| title |
|---|
| Monsters, Inc. |
| Finding Nemo |
| The Incredibles |
| Cars |
| Ratatouille |
| WALL-E |
| Up |
| Toy Story 3 |

**Question-3:** *Find the movies not released in the years between 2000 and 2010.*

**Query:** `SELECT title FROM movies WHERE year NOT BETWEEN 2000 AND 2010;`

**Output:**

| title |
|---|
| Toy Story |
| A Bug's Life |
| Toy Story 2 |
| Cars 2 |
| Brave |
| Monsters University |

**Question-4:** *Find the first 5 Pixar movies and their release year.*

**Query:** `SELECT title, year FROM movies LIMIT 5;`

**Output:**

| title |
|---|
| Toy Story |
| A Bug's Life |
| Toy Story 2 |
| Monsters, Inc. |
| Finding Nemo |