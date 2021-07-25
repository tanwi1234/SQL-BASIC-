# SQL-BASIC-
REVISION NOTES OF SQL
<h1 align="center">STRUCTURED QUERY LANGUAGE(SQL)</h1>
Structured Query Language or SQL is a standard Database language which is used to create, maintain and retrieve the data from relational databases like MySQL, Oracle, SQL Server, PostGre, etc.
<ul>
<li>SQL is used when we have structured data (in the form of tables).Examples like MySQL, Oracle, SQL Server, PostGre, etc.</li>
<li>All databases that are not relational (or do not use fixed structure tables to store data) and therefore do not use SQL, are called NoSQL databases. Examples of NoSQL are MongoDB, DynamoDB, Cassandra, etc.</li>
         <li>SQL is case insensitive</li>
<li>Single line comments in SQL using “--” (double hyphen) and multi lines”/* */”at the   beginning of any line</li>

</ul>
<h3> Relational Database-</h3>

Relational database means the data is stored as well as retrieved in the form of relations (tables).
<ul>
         <li><b>Attribute<b>: Attributes are the properties that define a relation.</li>
                  <li><b>Tuple<b>: Each row in the relation is known as tuple. </li>
                           <li><b>Degree</b>: The number of attributes in the relation is known as degree of  the relation.</li>
                           <li><b>Cardinality</b>: The number of tuples in a relation is known as cardinality. </li>
                           <li><b>Column</b>: Column represents the set of values for a particular attribute. </li>

</ul>

Queries deal with relational databases-

<ul>
         <li>Data Definition Language: It is used to define the structure of the database. e.g; CREATE TABLE, ADD COLUMN, DROP COLUMN and so on.</li>

         <li>Data Manipulation Language: It is used to manipulate data in the relations. e.g.; INSERT, DELETE, UPDATE and so on.</li>

         <li>Data Query Language: It is used to extract the data from the relations</li>

                           </ul>
A generic query to retrieve from a relational database is:
1.	SELECT [DISTINCT] Attribute_List FROM R1,R2….RM
2.	[WHERE condition]
3.	[GROUP BY (Attributes)[HAVING condition]]
4.       [ORDER BY(Attributes)[DESC]];
5.       ORDER BY AGE is equivalent to ORDER BY AGE ASC. If we want to retrieve the results in descending order of AGE, we can use ORDER BY AGE DESC.
6.        If we want to retrieve distinct values of an attribute or group of attribute, DISTINCT is used as in
7.	If we want to retrieve all attributes of students, we can write * in place of writing all attributes
                           	 

<h3>AGGREGRATION FUNCTIONS</h3>: Aggregation functions are used to perform mathematical operations on data values of a relation.
                           <ul>
                                    <li>All aggregation functions return only 1 row.</li>

                                    <li>COUNT: Count function is used to count the number of rows in a relation.</li> 
                                    <li>SUM: SUM function is used to add the values of an attribute in a relation.</li> 

                                    <li>AVERAGE: It gives the average values of the tupples.  Syntax:AVG(attributename)</li>
OR
Syntax:SUM(attributename)/COUNT(attributename)
                                    <li>MAXIMUM:It extracts the maximum value among the set of tupples.</li>
Syntax:MAX(attributename)

                                    <li>MINIMUM:It extracts the minimum value amongst the set of all the tupples.</li>
Syntax:MIN(attributename)

                                    <li>GROUP BY: Group by is used to group the tuples of a relation    based    on an attribute or group of attribute. It is always combined with aggregation function which is computed on group</li>


<li>An attribute which is not a part of GROUP BY clause can’t be used for selection. Any attribute which is part of GROUP BY CLAUSE can be used for selection but it is not mandatory. But we could use attributes which are not a part of the GROUP BY clause in an aggregrate function.</li>

                           </ul>
<h3>SQL COMMANDS</h3>

 
                           <h3>DDL (Data Definition Language)</h3>
It is used to define the structure of the database. e.g; CREATE TABLE, ADD COLUMN, DROP COLUMN and so on
DDL commands:
                           <ul>
CREATE : to create objects in database
ALTER : alters the structure of database
DROP : delete objects from database
RENAME : rename an objects
                           </ul>
                           
<h3>DML(Data Manipulation Language)</h3>
It is used to manipulate data in the relations. e.g.; INSERT, DELETE, UPDATE and so on.

SELECT: retrieve data from the database
INSERT: insert data into a table
UPDATE: update existing data within a table
DELETE: deletes all records from a table, space for the records remain

<h3>TCL(Transaction Control Language)</h3>

Transaction Control Language commands are used to manage transactions in the database
TCL commands:
COMMIT: Commit command is used to permanently save any transaction into the database.
ROLLBACK: This command restores the database to last committed state.It is also used with savepoint command to jump to a savepoint in a transaction.
SAVEPOINT: Savepoint command is used to temporarily save a transaction so that you can rollback to that point whenever necessary.

<h3>DCL (Data Control Language) :</h3>

A Data Control Language is a syntax similar to a computer programming language used to control access to data stored in a database (Authorization).
DCL commands:
GRANT: allow specified users to perform specified tasks.
REVOKE: cancel previously granted or denied permissions.

<h3>TRANSACTIONS</h3>
Transactions group a set of tasks into a single execution unit. 
Each transaction begins with a specific task and ends when all the tasks in the group successfully complete. 
If any of the tasks fail, the transaction fails.
Therefore, a transaction has only two results: success or failure. 
Incomplete steps result in the failure of the transaction.
 A database transaction, by definition, must be atomic, consistent, isolated and durable. These are popularly known as 
ACID properties.

<h3>Commands</h3>
BEGIN TRANSACTION: BEGIN TRANSACTION transaction_name ;
SET TRANSACTION: Places a name on a transaction
COMMIT: If everything is in order with all statements within a single transaction, all changes are recorded together in the database is called committed. 
ROLLBACK: If any error occurs with any of the SQL grouped statements, all changes need to be aborted. The process of reversing changes is called rollback.
SAVEPOINT: creates points within the groups of transactions in which to ROLLBACK. 
A SAVEPOINT is a point in a transaction in which you can roll the transaction back to a certain point without rolling back the entire transaction. 
RELEASE SAVEPOINT:- This command is used to remove a SAVEPOINT that you have created. 

Syntax: 
•	BEGIN TRANSACTION transaction_name ;
•	SET TRANSACTION [ READ WRITE | READ ONLY ];
•	DELETE FROM Student WHERE AGE = 20;
COMMIT;( saves all the transactions to the database since the last COMMIT or ROLLBACK command. )
•	DELETE FROM Student WHERE AGE = 20;
ROLLBACK; ( used to undo transactions since the last commit or roolback command issued)
•	SAVEPOINT SAVEPOINT_NAME;
•	ROLLBACK TO SAVEPOINT_NAME; (ROLLBACK to any SAVEPOINT at any time to return the appropriate data to its original state. )
•	RELEASE SAVEPOINT SAVEPOINT_NAME

  <h3> VIEWS</h3>
Views in SQL are kind of virtual tables.
 A view also has rows and columns as they are in a real table in the database.
A View can either have all the rows of a table or specific rows based on certain condition.
create a view by selecting fields from one or more tables present in the database.

Uses of a View :
A good database should contain views due to the given reasons:
1.	Restricting data access –
Views provide an additional level of table security by restricting access to a predetermined set of rows and columns of a table.
2.	Hiding data complexity –
A view can hide the complexity that exists in a multiple table join.
3.	Simplify commands for the user –
Views allows the user to select information from multiple tables without requiring the users to actually know how to perform a join.
4.	Store complex queries –
Views can be used to store complex queries.
5.	Rename Columns –
Views can also be used to rename the columns without affecting the base tables provided the number of columns in view must match the number of columns specified in select statement. Thus, renaming helps to to hide the names of the columns of the base tables.
6.	Multiple view facility –
Different views can be created on the same table for different users.

COMMANDS:
CREATE VIEW:
CREATE VIEW DetailsView AS
SELECT NAME, ADDRESS
FROM StudentDetails
WHERE S_ID < 5;
SELECT * FROM DetailsView;

(CREATE VIEW FROM MULTIPLE TABLES)
CREATE VIEW MarksView AS
SELECT StudentDetails.NAME, StudentDetails.ADDRESS, StudentMarks.MARKS
FROM StudentDetails, StudentMarks
WHERE StudentDetails.NAME = StudentMarks.NAME;

DELETED VIEWS: DROP VIEW MarksView;
UPDATE VIEWS: There are certain conditions needed to be satisfied to update a view. 
•	The SELECT statement which is used to create the view should not include   GROUP BY  clause or ORDER BY clause.
•	The SELECT statement should not have the DISTINCT keyword.
•	The View should have all NOT NULL values.
•	The view should not be created using nested queries or complex queries.
•	The view should be created from a single table. If the view is created using multiple tables then we will not be allowed to update the view.

CREATE OR REPLACE VIEW MarksView AS
SELECT StudentDetails.NAME, StudentDetails.ADDRESS,StudentMarks.MARKS, StudentMarks.AGE
FROM StudentDetails, StudentMarks
WHERE StudentDetails.NAME = StudentMarks.NAME;

INSERTING IN ROW:
INSERT INTO DetailsView(NAME, ADDRESS)
VALUES("Suresh","Gurgaon");

DELETING A ROW FROM VIEW:
DELETE FROM DetailsView
WHERE NAME="Suresh";

<h3>WITH CHECK OPTION:</h3>
•	The WITH CHECK OPTION clause is used to prevent the insertion of rows in the view where the condition in the WHERE clause in CREATE VIEW statement is not satisfied.
•	If we have used the WITH CHECK OPTION clause in the CREATE VIEW statement, and if the UPDATE or INSERT clause does not satisfy the conditions then they will return an error.

CREATE VIEW SampleView AS
SELECT S_ID, NAME
FROM  StudentDetails
WHERE NAME IS NOT NULL
WITH CHECK OPTION;
•	In this View if we now try to insert a new row with null value in the NAME column then it will give an error because the view is created with the condition for NAME column as NOT NULL
.
<h3>CONSTRAINTS:</h3>

Constraints are the rules that we can apply on the type of data in a table. That is, we can specify the limit on the type of data that can be stored in a particular column in a table using constraint
Constraints in sql:
NOT NULL:
UNIQUE
PRIMARY KEY
FOREIGN KEY
CHECK
DEFAULT

<h3>INDEXES:</h3>
An index is a schema object. 
It is used by the server to speed up the retrieval of rows by using a pointer.
 It can reduce disk I/O(input/output) by using a rapid path access method to locate data quickly. 
An index helps to speed up select queries and where clauses, but it slows down data input, with the update and the insert statements. 
Indexes can be created or dropped with no effect on the data. 

<h3>TRIGGER:</h3>
A trigger is a stored procedure in database which automatically invokes whenever a special event in the database occurs. For example, a trigger can be invoked when a row is inserted into a specified table or when certain table columns are being updated.

EXAMPLE:
In such schema, create a trigger so that the total and average of specified marks is automatically inserted whenever a record is insert.
create trigger stud_marks 
before INSERT 
on 
Student 
for each row 
set Student.total = Student.subj1 + Student.subj2 + Student.subj3, Student.per = Student.total * 60 / 100;


For example, given Library Book Management database schema with Student database schema. In these databases, if any student borrows a book from library then the count of that specified book should be decremented. 

create trigger book_copies_deducts 
after INSERT 
on book_issue 
for each row 
update book_det set copies = copies - 1 where bid = new.bid; 

