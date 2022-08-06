# Parameterised statements

A specific SQL injection software defense is the use of parameterised statements: 
[Give me parameterised SQL, or give me death](https://blog.codinghorror.com/give-me-parameterized-sql-or-give-me-death/). 
Instead of concatenating strings, use secure database components such as stored procedures, parametrised queries, and 
object bindings for commands, or an Object-Relational Mapping (ORM) library.

* A prepared statement is a reference to a pre-interpreted query routine on the database, ready to accept parameters
* A parametrised query is a query made by the code in such a way that values are passed in alongside some SQL that 
has placeholder values, like `?` or `%s`.

For a parameterised query to be effective in preventing SQL injection, the string that is used in the query must 
always be a hard-coded constant, and is not to contain **any** variable data from **any** origin. Do not be tempted 
to decide this in a case-by-case manner whether an item of data can be trusted, and continue using string concatenation 
within the query for cases that are considered safe. It is all too easy to make a mistakes about possible origin, 
or for changes in other code to violate assumptions about what data is tainted. 

Many database engines have concepts of a prepared statement that can be constructed explicitly with plaintext query 
syntax, then reused over the lifetime of a client's session. Sometimes the query plan can be 
[cached](../coding/cache.md).

Parametrised queries do not always use a prepared statement under the hood; they should do so if possible, but sometimes 
it is just formatting in the parameter values. The difference between a prepared statement and a parametrised query
is the shape of the API used.

## Articles

* [Python MySQL Execute Parameterized Query using Prepared Statement](https://pynative.com/python-mysql-execute-parameterized-query-using-prepared-statement/)
* [MySQLJS Performing queries](https://github.com/mysqljs/mysql#performing-queries)