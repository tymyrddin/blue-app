# Parameterized statements

A specific SQL injection software defense is the use of parameterised statements. 
[Give me parameterised SQL, or give me death](https://blog.codinghorror.com/give-me-parameterized-sql-or-give-me-death/). 
Instead of concatenating strings, use secure database components such as stored procedures, parametrised queries, and 
object bindings for commands, or an Object-Relational Mapping (ORM) library.

For example, in Java uses a PreparedStatement class rather than concatenating the user-provided strings in a query.
