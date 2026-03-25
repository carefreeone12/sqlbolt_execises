# SQL Lesson 3: Queries with constraints (Pt. 2)
SQL facilitates text-based data filtering within the `WHERE` clause using operators designed for exact case-sensitive matches (`=`, `!=`), case-insensitive comparisons (`LIKE`, `NOT LIKE`), and list inclusion (`IN`). Wildcard characters, specifically `%` for variable-length sequences and `_` for single characters, provide robust pattern-matching capabilities. Syntactically, all string values must be enclosed in quotes to distinguish them from native SQL keywords. While native SQL operators are efficient for standard queries, complex or large-scale full-text search operations are optimally handled by dedicated search engines like Apache Lucene or Sphinx.

## Exercise:
Apply the discussed string operators within a `WHERE` clause to filter the dataset and complete the following tasks.

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

**Question-1** *Find all the Toy Story movies.*

**Query:** `SELECT * FROM movies WHERE title LIKE "%Toy Story%";`

**Output:**

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |

**Question-2:** *Find all the movies directed by John Lasseter.*

**Query:** `SELECT * FROM movies WHERE director = 'John Lasseter';`

**Output:**

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 1 | Toy Story | John Lasseter | 1995 | 81 |
| 2 | A Bug's Life | John Lasseter | 1998 | 95 |
| 3 | Toy Story 2 | John Lasseter | 1999 | 93 |
| 7 | Cars | John Lasseter | 2006 | 117 |
| 12 | Cars 2 | John Lasseter | 2011 | 120 |

**Question-3:** *Find all the movies (and director) not directed by John Lasseter.*

**Query:** `SELECT * FROM movies WHERE director != 'John Lasseter';`

**Output:**

| id | title | director | year | length_minutes |
|---|---|---|---|---|
| 4 | Monsters, Inc. | Pete Docter | 2001 | 92 |
| 5 | Finding Nemo | Andrew Stanton | 2003 | 107 |
| 6 | The Incredibles | Brad Bird | 2004 | 116 |
| 8 | Ratatouille | Brad Bird | 2007 | 115 |
| 9 | WALL-E | Andrew Stanton | 2008 | 104 |
| 10 | Up | Pete Docter | 2009 | 101 |
| 11 | Toy Story 3 | Lee Unkrich | 2010 | 103 |
| 13 | Brave | Brenda Chapman | 2012 | 102 |
| 14 | Monsters University | Dan Scanlon | 2013 | 110 |
| 87 | WALL-G | Brenda Chapman | 2042 | 97 |

**Question-4:** *Find all the WALL-* movies.

**Query:** `SELECT title FROM movies WHERE title LIKE "WALL%";`

**Output:**

| title |
|---|
| WALL-E |
| WALL-G |