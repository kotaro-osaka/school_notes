# Subquery
___
## Subquery vs. Join
- Can often be replaced with joins because both achieve similar results using different approaches
### Performance
- Joins are more efficient
- Especially with large datasets
- Query optimizer in most DMS can more easily optimize joins
- Subqueries may execute repeatedly for each row in outer query (leads to performance issues, especially with correlated subqueries)
### Clarity & Readability
- Join syntax more explicit & easier to understand
- Subqueries can be harder to read / debug
### Flexibility
- Joins more flexible in specifying table relationships & defining conditions for joining data
- Joins often provide more control over query execution
### Index Usage
- Joins can take advantage of indexes more effectively (better query performance)
- Subqueries can prevent optimizer from using indexes optimally (especially when involved with large result sets)
### Maintainability
- Joins easier to maintain / modify over time
- Join conditions are explicit & can be easily adjusted
## Types
### Scalar Subquery
- Returns single value
- Used in `SELECT` // `WHERE`
#### Example
```sql
SELECT column1, (SELECT MAX(column2) FROM table2) AS max_value
FROM table1;
```
- In this example, the subquery `(SELECT MAX(column2) FROM table2)` returns a single value, which is then used as part of the main query's result set.
### Row Subquery
- Returns one or more rows of data
- Used in comparisons with other tables or as source of data for `IN` // `EXISTS`
#### Example
```sql
SELECT column1
FROM table1
WHERE column2 IN (SELECT column2 FROM table2 WHERE condition);
```
- Here, the subquery `(SELECT column2 FROM table2 WHERE condition)` returns multiple rows, which are then compared against values in the main query's `column2`.
### Table Subquery (Inline View)
- Returns result set that can be treated as a table
- Used in `FROM`, acts as virtual table that can be joined with other tables / subqueries
#### Example
```sql
SELECT *
FROM (SELECT column1, column2 FROM table1 WHERE condition) AS subquery_alias;
```
- In this example, the subquery `(SELECT column1, column2 FROM table1 WHERE condition)` acts as a virtual table that can be joined or further manipulated in the main query.
### Correlated Subquery
- Depends on values from outer query
- Executed repeatedly for each row processed by outer query
#### Example
```sql
SELECT column1
FROM table1 t1
WHERE column1 = (SELECT MAX(column2) FROM table2 WHERE table2.column3 = t1.column3);
```
- Here, the subquery `(SELECT MAX(column2) FROM table2 WHERE table2.column3 = t1.column3)` is correlated with the outer query `table1`. It is executed for each row in `table1` and depends on the value of `t1.column3`.
## Aggregate Functions
- `Count()`
- `Sum()`
- `AVG()`
- `Max()`
- `Min()`
