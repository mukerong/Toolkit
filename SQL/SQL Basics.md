<h1>SQL Basics</h1>

<hr />

<h2>Table of Content</h2>

<ul>
<li><a href="#definition">Definition</a></li>
<li><a href="#database">Database</a>

<ul>
<li><a href="#create-database">CREATE DATABASE</a></li>
<li><a href="#drop-database">DROP DATABASE</a></li>
<li><a href="#show-database">SHOW DATABASE</a></li>
</ul></li>
<li><a href="#table">Table</a>

<ul>
<li><a href="#create-table">CREATE TABLE</a></li>
<li><a href="#drop-table">DROP TABLE &amp; TRUNCATE TABLE</a></li>
<li><a href="#alter-table">ALTER TABLE</a></li>
<li><a href="#insert-into">INSERT INTO</a></li>
<li><a href="#delete">DELETE</a></li>
<li><a href="#update">UPDATE</a></li>
<li><a href="#select-into">SELECT INTO</a></li>
<li><a href="#constraints">Constraints</a>

<ul>
<li><a href="#not-null">NOT NULL</a></li>
<li><a href="#unique">UNIQUE</a></li>
<li><a href="#primary-key">PRIMARY KEY</a></li>
<li><a href="#foreign-key">FOREIGN KEY</a></li>
<li><a href="#check">CHECK</a></li>
<li><a href="#default">DEFAULT</a></li>
<li><a href="#create-index">CREATE INDEX</a></li>
<li><a href="#auto-increment">AUTO INCREMENT</a></li>
</ul></li>
</ul></li>
<li><a href="#query">Query</a>

<ul>
<li><a href="#create-view">CREATE VIEW</a></li>
<li><a href="#select">SELECT</a></li>
<li><a href="#select-distinct">SELECT DISTINCT</a></li>
<li><a href="#where">WHERE</a></li>
<li><a href="#and-or">AND &amp; OR</a></li>
<li><a href="#between">BETWEEN</a></li>
<li><a href="#in">IN</a></li>
<li><a href="#like">LIKE</a></li>
<li><a href="#regex">REGEXP</a></li>
<li><a href="#limit">LIMIT</a></li>
<li><a href="#select-top">SELECT TOP</a></li>
<li><a href="#order-by">ORDER BY</a></li>
<li><a href="#aliases">Aliases</a></li>
<li><a href="#join">JOIN</a>

<ul>
<li><a href="#inner-join">INNER JOIN</a></li>
<li><a href="#left-right-join">LEFT JOIN &amp; RIGHT JOIN</a></li>
<li><a href="#full-join">FULL OUTER JOIN</a></li>
</ul></li>
<li><a href="#union">UNION</a></li>
<li><a href="#null">NULL</a></li>
<li><a href="#aggregate-function">Aggregate Functions</a></li>
<li><a href="#group-by">GROUP BY</a></li>
<li><a href="#having">HAVING</a></li>
<li><a href="#comments">Comments</a></li>
</ul></li>
<li><a href="#resources">Resources</a></li>
</ul>

<hr />

<h3 id="definition">Definition</h3>

<p>SQL (pronounced &#8216;S-Q-L&#8217; or &#8216;ess-que-el&#8217;) stands for Structured Query Language. It is used to communicate with a database. People can use SQL statements to update data on a database, retrieve data from a database and so on. In my opinion, this is the most important language to use when working with database.</p>

<p>You may wonder why we need to communicate with a database, can we just save all the data in a big Excel file? Well, this about this, the maximum rows excel can saved are a little more than 1 million. This means people cannot save data for more than 1 million. Also, even though Excel can save thousands of data, the speed will be very slow. Sometimes, Excel could freeze the computer for several mins (maybe even hours).</p>

<p>Therefore, to maintain a database, learning SQL can be the most important things. Luckily, SQL language is very simple and easy to learn. There are not many commands needs to be remember, and those commands can be used to accomplish almost everything that one needs to do with a database.</p>

<h3 id="database">Database</h3>

<p>Database contains aggregations of data records or files. SQL can help build and maintain database. </p>

<h4 id="create-database">CREATE DATABASE Statement</h4>

<p>To create a database, you need to use <code>CREATE DATABASE</code> statement. </p>

<p><em>Syntax:</em></p>

<pre><code>CREATE DATABASE database_name;
</code></pre>

<h4 id="drop-database">DROP DATABASE Statement</h4>

<p>To drop an existing database, you can use <code>DROP DATABASE</code> statement.</p>

<p><em>Syntax:</em></p>

<pre><code>DROP DATABASE database_name;
</code></pre>

<p>All the information in the dropped database will be lost, so be careful before dropping a database.</p>

<h4 id="show-database">SHOW DATABASE Statement</h4>

<p>After creating or dropping a database, you may want to check it in the list of databases. </p>

<p><em>Syntax:</em></p>

<pre><code>SHOW DATABASES (LIKE pattern);
</code></pre>

<p>The System will return a list of databases. If there is no <code>LIKE</code> clause, all the databases name will be listed. </p>

<h3 id="table">Table</h3>

<p>Within a database, data are saved in the format of tables, which is the same format as an Excel file. </p>

<p>&#8216;US_City&#8217;</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>Tables have their unique name to help one identify. The table I will use in this article a lot named &#8216;City in US&#8217;. </p>

<p>Tables will contains &#8216;rows&#8217; and &#8216;columns&#8217;. Columns contain the column name, data type and other attributes. Rows contain the records, the actual data one wants. For the table above, columns are &#8216;City&#8217;, &#8216;State&#8217; and &#8216;Country&#8217;. Rows examples are &#8216;New York City, NY, US&#8217;.</p>

<h4 id="create-table">CREATE TABLE Statement</h4>

<p>After creating a database, it is time to create a table within the database. To create a new table, you can use <code>CREATE TABLE</code> statement.</p>

<p><em>Syntax:</em></p>

<pre><code>CREATE TABLE Table_name (
    column1 datatype,
    column2 datatype,
    ...
);
</code></pre>

<p>Datatype will define the required data type within the column. You can find the complete list in <a href="https://www.w3schools.com/sql/sql_datatypes.asp">W3school Website</a>. It has data types and ranges for Microsoft Access, MySQL and SQL Serve. Different servers will have different data type name, so always check the document when set up a new table. Here are some data types for MySQL. </p>

<ul>
<li>Text Types

<ul>
<li>VARCHAR(size)</li>
<li>TEXT</li>
</ul></li>
<li>Number Types

<ul>
<li>INT(size)</li>
<li>FLOAT(size, d)</li>
</ul></li>
<li>Date Types

<ul>
<li>DATE()</li>
<li>TIME()</li>
<li>YEAR()</li>
</ul></li>
</ul>

<p>To make things easier, if you want to create using an existing table, you can use the combination of <code>CREATE TABLE</code> statement and the <code>SELECT</code> statement.</p>

<p><em>Syntax:</em></p>

<pre><code>CREATE TABLE new_table_name AS 
    SELECT column1, column2, ...
    FROM existing_table_name
    WHERE condition;
</code></pre>

<h4 id="drop-table">DROP TABLE Statement &amp; TRUNCATE TABLE Statement</h4>

<p>To drop an existing table, you can use <code>DROP TABLE</code> statement.</p>

<p><em>Syntax:</em></p>

<pre><code>DROP TABLE table_name;
</code></pre>

<p>To only delete the data inside a table not the table itself, you can use <code>TRUNCATE TABLE</code> Statement.</p>

<p><em>Syntax:</em></p>

<pre><code>TRUNCATE TABLE table_name:
</code></pre>

<p>The data inside the table will be delete, but the format of the table will keep.</p>

<h4 id="alter-table">ALTER TABLE Statement</h4>

<p>You have learnt to use <code>INSERT INTO</code> statement to add rows into a table. How about columns? <code>ALTER TABLE</code> statement is used to add, delete, or modify columns in an existing table.</p>

<p><em>Syntax - Add Column</em></p>

<pre><code>ALTER TABLE table_name
ADD column_name datatype;
</code></pre>

<p><em>Syntax - Drop Column</em></p>

<pre><code>ALTER TABLE table_name
DROP COLUMN column_name;
</code></pre>

<p><em>Syntax - Modify Column</em></p>

<pre><code>ALTER TABLE table_name
ALTER COLUMN column_name datatype.
</code></pre>

<h4 id="insert-into">INSERT INTO Statement</h4>

<p>All the statements and clauses we learnt above are about retrieve data from a database. Let&#8217;s move on to a new area: updating the table.</p>

<p><code>INSERT INTO</code> statement is used to insert new records in a table. Here is the syntax:</p>

<p>To specify the column names and the values:</p>

<pre><code>INSERT INTO table_name (column1, column2 ...)
VALUES (value1, value2, ...);
</code></pre>

<p>To add values for all the columns of the table:</p>

<pre><code>INSERT INTO table_name
VALUES (value1, value2, ...); /* (Remember the comment sign?) Make sure the order of the value is the same with the columns in the table. */
</code></pre>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<pre><code>INSERT INTO US_City
VALUES ('Champaign', 'IL', 'US');
</code></pre>

<p>Normally, the system will show the table has been updated, but not display what we have added. We need to use <code>SELECT</code> statement to display the result. The result will be something like:</p>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
<tr>
	<td>Champaign</td>
	<td>IL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>To Specify the column:</p>

<pre><code>INSERT INTO US_City (City, Country)
VALUES ('Champaign', 'US');
</code></pre>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
<tr>
	<td>Champaign</td>
	<td>null</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>Note that the column without value will show as &#8216;null&#8217;. </p>

<h4 id="delete">DELETE Statement</h4>

<p>To delete existing records in a table, we need to use <code>DELETE</code> statement.</p>

<p><em>Syntax:</em></p>

<pre><code>DELETE FROM table_name
WHERE condition;
</code></pre>

<p><strong>Be careful when using <code>DELETE</code> Statement. If there is no <code>WHERE</code> clause, all the records will be deleted!!</strong></p>

<p><em>Example:</em></p>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<pre><code>DELETE FROM US_City
WHERE City = 'Chicago';
</code></pre>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<h4 id="update">UPDATE Statement</h4>

<p>If you want to modify the existing records in a table, you can use <code>DELETE</code> and <code>INSERT INTO</code>, which is very tedious. <code>UPDATE</code> statement can be a better choice. <code>UPDATE</code> statement is used to modify the existing records in a table.</p>

<p><em>Syntax:</em></p>

<pre><code>UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
</code></pre>

<p><strong>Like <code>DELETE</code> statement, you also need to be careful when updating records. If there is no <code>WHERE</code> clause, all the records will be update!!</strong></p>

<p><em>Example:</em></p>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<pre><code>UPDATE US_City
SET State = 'NJ'
WHERE City = 'Miami'; -- Just kidding :)
</code></pre>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>NJ</td>
	<td>US</td>
</tr>
</tbody>
</table>

<h4 id="select-into">SELECT INTO Statement</h4>

<p>When you work with a table, you may want to copy information from one table into another. <code>SELECT INTO</code> statement can help copy data from one table to another.</p>

<p><em>Syntax:</em></p>

<pre><code>SELECT column_name(s)
INTO newtable
FROM table1;
</code></pre>

<p>The new table will be created based on the column names in <code>SELECT</code> statement. You can use Alias to change the name.</p>

<p><em>Example:</em></p>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<pre><code>SELECT *
INTO IL_City
FROM US_City
WHERE State = 'IL';
</code></pre>

<p>&#8216;IL_City&#8217;</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>Springfield</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<p><em>Tips:</em></p>

<p>To create an empty table with the shema of another, you can add the <code>WHERE</code> clause that the conditions will always be false.</p>

<p><em>Example:</em></p>

<pre><code>SELECT *
INTO IL_City
FROM US_City
WHERE 0 = 1
</code></pre>

<h4 id="constraints">Constraints</h4>

<p>When <code>CREATE TABLE</code> or <code>ALTER TABLE</code>, you can specify some rules for the data in a table. Constraints are used to limit the type of data within a table to ensure the accuracy. They are like &#8216;Data Validation&#8217; in Excel. Constraints can be applied to both column level and table level. </p>

<p><em>Syntax</em></p>

<pre><code>CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    ...
);
</code></pre>

<h5 id="not-null">NOT NULL</h5>

<p>As explained previously, if there is no value within a table, SQL will save it as &#8216;null&#8217;. NOT NULL constraint enforces a column to always contain a value. </p>

<p><em>Syntax</em></p>

<pre><code>CREATE TABLE table_name(
    column1 datatype NOT NULL,
    column2 datatype,
    ...
);
</code></pre>

<p>Because of the &#8216;NOT NULL&#8217; constraint, when you want to insert a new record in this table, you cannot put nothing for column1.</p>

<h5 id="unique">UNIQUE</h5>

<p>UNIQUE constraint forces that all values in a column are different. You may need this when you assign individual ID to each record.</p>

<p><em>Syntax - Create Table</em></p>

<pre><code>CREATE TABLE table_name(
    column1 datatype UNIQUE
    ...
);
</code></pre>

<p>In MySQL, the Syntax is a little bit different:</p>

<pre><code>CREATE TABLE (
    column1 datatype,
    ...
    UNIQUE (column1)
</code></pre>

<p>There might be chances that you do not want value within one column to be unique. Instead, you want value based on the combination of several columns to be unique. You can use the following syntax for all SQL server, and you can name this combination as well.</p>

<p><em>Syntax - Combine Several Columns</em></p>

<pre><code>CREATE TABLE table_name(
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ...
    CONSTRAINT name_of_this_combination UNIQUE (column1, column2)
);
</code></pre>

<p><em>Syntax - Alter Table</em></p>

<pre><code>ALTER TABLE table_name
ADD UNIQUE (column_name);
</code></pre>

<p><em>Syntax - Alter Table &amp; Combine Several Columns</em></p>

<pre><code>ALTER TABLE table_name
ADD CONSTRAINT name UNIQUE (column1, column2);
</code></pre>

<p><em>Syntax - Drop UNIQUE Constrain</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
DROP INDEX constraint_name;
</code></pre>

<p>Others:</p>

<pre><code>ALTER TABLE table_name
DROP CONSTRAINT constraint_name;
</code></pre>

<h5 id="primary-key">PRIMARY KEY</h5>

<p>PRIMARY KEY is a unique identification of reach record in a table. To use Excel as an example, the PRIMARY KEY in excel is the row number. Since it is unique, PRIMARY KEY must contain UNIQUE values and cannot contain NULL values. Each table can only have one PRIMARY key. </p>

<p><em>Syntax - Create Table</em></p>

<p>MySQL:</p>

<pre><code>CREATE TABLE table_name(
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    PRIMARY KEY (column1)
);
</code></pre>

<p>Others:</p>

<pre><code>CREATE TABLE table_name(
    column1 datatype constraint PRIMARY KEY,
    column2 datatype constraint,
    column3 datatype constraint,
);

Similar to UNIQUE, you can create PRIMARY KEY by combining several columns together. You can also name it as well.

</code></pre>

<p>CREATE TABLE table_name(
 column1 datatype constraint,
 column2 datatype constraint,
 column3 datatype constraint,
 CONSTRAINT constraint_name PRIMARY KEY (column1, column2,&#8230;)
);
```</p>

<p><em>Syntax - Alter Table</em></p>

<p>Single column:</p>

<pre><code>ALTER TABLE table_name
ADD PRIMARY KEY (column_name);
</code></pre>

<p>Multiple columns:</p>

<pre><code>ALTER TABLE table_name
ADD CONSTRAINT constraint_name PRIMARY KEY (column1, column2, ...);
</code></pre>

<p>Please note that the column you pick cannot contain null value.</p>

<p><em>Syntax - Drop PRIMARY KEY</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
DROP PRIMARY KEY;
</code></pre>

<p>Others:</p>

<pre><code>ALTER TABLE table_name
DROP CONSTRAINT constraint_name;
</code></pre>

<h5 id="foreign-key">FOREIGN KEY</h5>

<p>FOREIGN KEY works together with PRIMARY KEY to link tables together. </p>

<p>Assume you have created a US_City table with PRIMARY KEY on City_Code column. You have another table called US_City_Temperature to show up the temperature for each city without showing the city name. </p>

<p>US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City_Code</th>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>0002</td>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>0003</td>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>9999</td>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>&#8216;US_City_Temperature&#8217;</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City_Code</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>0001</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>0001</td>
	<td>54</td>
	<td>1/2/2016</td>
</tr>
<tr>
	<td>0001</td>
	<td>55</td>
	<td>1/3/2016</td>
</tr>
<tr>
	<td>0002</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>9998</td>
	<td>79</td>
	<td>1/1/2016</td>
</tr>
</tbody>
</table>

<p>Note that the City_Code column in the US_City_Temperature table points to the City_Code column in US_City table. The City_Code column in US_City table is the PRIMARY KEY, and the City_Code column in the US_City_Temperature is a FOREIGN KEY. </p>

<p>FOREIGN KEY constraint prevents invalid data from being inserted into the foreign key column because it has to be one of the values in the table it points to (the PRIMARY KEY). These two keys are very useful when <code>JOIN</code> tables together.</p>

<p><em>Syntax - Create Table</em></p>

<p>MySQL</p>

<pre><code>CREATE TABLE table_name(
    column1 datatype constraint,
    column2 datatype constraint,
    ...
    PRIMARY KEY (column_name),
    FOREIGN KEY (column_name) REFERENCES another_table(primary_key_column);
);
</code></pre>

<p>Others</p>

<pre><code>CREATE TABLE table_name(
    column1 datatype constraint PRIMARY KEY,
    column2 datatype constraint
    column3 datatype constraint FOREIGN KEY REFERENCES another_table(primary_key_column);
);
````

*Syntax - Add FOREIGN KEY*

Single Column

</code></pre>

<p>ALTER TABLE table_name
ADD FOREIGN KEY (column_name) REFERENCES another_table (primary_key_column);
```</p>

<p>Multiple Columns</p>

<pre><code>ALTER TABLE table_name
ADD CONSTRAINT foreign_key_column_name
FOREIGN KEY (column_name) REFERENCES another_table (primary_key_column);
</code></pre>

<p><em>Syntax - Drop FOREIGN KEY</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
DROP FOREIGN KEY column_name;
</code></pre>

<p>Others</p>

<pre><code>ALTER TABLE table_name
DROP CONSTRAINT column_name;
</code></pre>

<h5 id="check">CHECK</h5>

<p>CHECK constraints limit the value range in a column. It is similar to Data Validation in Excel. </p>

<p>When defining a CHECK constraint within a column, it will allow certain values for this column. When defining a CHECK constraint within a table, it will limit the values in certain columns based on the values in other columns.</p>

<p><em>Syntax - Create Table</em></p>

<p>Single Column</p>

<p>MySQL </p>

<pre><code>CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ...
    CHECK (column2 condition)
);
</code></pre>

<p>Others</p>

<pre><code>CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype CHECK (column3 condition)
);
</code></pre>

<p>Multiple Column</p>

<pre><code>CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ...
    CONSTRAINT constraint_name CHECK (column1 condition AND|OR column2 condition)
);
</code></pre>

<p><em>Syntax - Add CHECK</em></p>

<p>Single Column</p>

<pre><code>ALTER TABLE table_name
ADD CHECK (column condition)
</code></pre>

<p>Multiple Columns</p>

<pre><code>ALTER TABLE table_name
ADD CONSTRAINT constraint_name CHECK (column1 condition AND|OR column2 condition)
);
</code></pre>

<p><em>Syntax - Drop CHECK</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
DROP CHECK constraint_name;
</code></pre>

<p>Others</p>

<pre><code>ALTER TABLE table_name
DROP CONSTRAINT constraint_name;
</code></pre>

<h5 id="default">DEFAULT</h5>

<p>DEFAULT constraint is used to provide a default value to a new record if there is no value specified.</p>

<p><em>Syntax - Create Table</em></p>

<pre><code>CREATE TABLE table_name (
    column1 datatype DEFAULT default_value,
    column2 datatype constraint,
    ...
);
</code></pre>

<p><em>Syntax - Add DEFAULT</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
ALTER column_name SET DEFAULT default_value;
</code></pre>

<p>Oracle</p>

<pre><code>ALTER TABLE table_name
MODIFY column_name DEFAULT default_value;
</code></pre>

<p>Others</p>

<pre><code>ALTER TABLE table_name
ALTER COLUMN column_name SET DEFAULT default_value;
</code></pre>

<p><em>Syntax - Drop DEFAULT</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
ALTER column DROP DEFAULT;
</code></pre>

<p>Others</p>

<pre><code>ALTER TABLE table_name
ALTER COLUMN column_name DROP DEFAULT;
</code></pre>

<h5 id="create-index">CREATE INDEX Statement</h5>

<p>Indexes are used to retrieve data from the database very fast. They cannot been seen by users. Updating a table with indexes takes longer, so only create indexes on necessary columns.</p>

<p><em>Syntax</em></p>

<pre><code>CREATE INDEX index_name
ON table_name (column1, column2, ...);
</code></pre>

<p><em>Syntax - Unique</em></p>

<pre><code>CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);
</code></pre>

<p><em>Syntax - Drop INDEX</em></p>

<p>MySQL</p>

<pre><code>ALTER TABLE table_name
DROP INDEX index_name;
</code></pre>

<p>SQL Server</p>

<pre><code>DROP INDEX table_name.index_name;
</code></pre>

<p>MS Access</p>

<pre><code>DROP INDEX index_name ON table_name;
</code></pre>

<p>DB2/Oracle</p>

<pre><code>DROP INDEX index_name;
</code></pre>

<h5 id="auto-increment">AUTO INCREMENT Field</h5>

<p>A unique number will be generated when user insert a new record. This is often the PRIMARY KEY field. </p>

<p><em>Syntax - MySQL</em></p>

<p>CREATE TABLE table_name (
 column1 datatype constraint AUTO_INCREMENT,
 column2 datatype constraint,
 &#8230;
 PRIMARY KEY (column1)
);</p>

<p>The default beginning value is 1, and increment by 1. To change this setting, need to use <code>ALTER TABLE</code>.</p>

<pre><code>ALTER TABLE column_name AUTO_INCREMENT = number_to_start;
</code></pre>

<p><code>AUTO INCREMENT</code> column will update automatically, so don&#8217;t need to specify the value of this column. </p>

<p><em>Syntax - SQL Server</em></p>

<pre><code>CREATE TABLE table_name (
    column1 datatype IDENTITY(start_point, increment) PRIMARY KEY
    column2 datatype constraint,
    ...
);
</code></pre>

<p>The start point and increment need to be specified.</p>

<p><em>Syntax - Access</em></p>

<pre><code>CREATE TABLE table_name (
    column1 datatype PRIMARY KEY AUTOINCREMENT(start_point, increment),
    column2 datatype constraint,
    ...
);
</code></pre>

<p>The start point and increment are optional. The default is 1 and 1.</p>

<p><em>Syntax - Oracle</em></p>

<pre><code>CREATE SEQUENCE seq_name
MINVALUE value
START WITH value
INCREMENT BY value
CACHE value;
</code></pre>

<p>The CACHE specifies how many sequence values will be stored in memory for faster access. </p>

<p>Unlike other server, Oracle needs to specify the increment column when user add a new record.</p>

<pre><code>INSERT INTO table_name (column1, column2...)
VALUES (seq_name.nextval, column_value1, ...);
</code></pre>

<h3 id="query">Basic Query</h3>

<p>SQL query can help user retrieve data from table in a selected database.</p>

<h4 id="create-view">CREATE VIEW Statement</h4>

<p><code>CREATE VIEW</code> can generate a virtual table based on the result-set of a SQL statement. It is an up to date view of a real table in a database.</p>

<p><em>Syntax - Create View</em></p>

<pre><code>CREATE VIEW view_name AS
SELECT *
FROM table_name
WHERE condition;
</code></pre>

<p><em>Syntax - Update View</em></p>

<pre><code>CREAT|REPLACE VIEW view_name AS
SQL_Query;
</code></pre>

<p><em>Syntax - Drop View</em></p>

<pre><code>DROP VIEW view_name;
</code></pre>

<h4 id="select">SELECT Statement</h4>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>This is a table containing all the cities in US. To select all the records in this table, this is a very simple SQL statement:</p>

<pre><code>SELECT * FROM US City;
</code></pre>

<ul>
<li><code>SELECT</code> is a SQL commands.</li>
<li><code>*</code> means &#8216;everything&#8217; in SQL.</li>
<li><code>FROM</code> tells the database which table you are looking for</li>
<li><code>US City</code> is the table name.</li>
<li><code>;</code> shows this statement has ended.</li>
</ul>

<p>Keep in mind that SQL keywords are NOT case sensitive, so <code>SELECT</code> is the same with <code>select</code>. Also remember to add a semicolon(;) after a SQL statement. This is a standard way to separate each SQL statement.</p>

<p>To select specific columns you are looking for, here is a more general way to use SELECT:</p>

<pre><code>SELECT column_name, column_name ...
FROM table_name;
</code></pre>

<p>In the &#8216;US City&#8217; table, it could be:</p>

<pre><code class="SELECT City">FROM US City;
</code></pre>

<p>Only the columns after <code>SELECT</code> will be shown in the results. To separate the column you want to choose, put a comma(,) between each column. Don&#8217;t forget the semicolon(;) after the statement. </p>

<h4 id="select-distinct">SELECT DISTINCT Statement</h4>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>Let&#8217;s assume the US City table right now is not very clean. There are a lot of duplicate records. If you only want to list the distinct values, you can use <code>SELECT DISTINCT</code> statement. The syntax looks like this:</p>

<pre><code>SELECT DISTINCT column_name, column_name...
FROM table_name;
</code></pre>

<p>In the US City example:</p>

<pre><code>SELECT DISTINCT City
FROM US City;
</code></pre>

<p>The result will look like this:</p>

<table>
<colgroup>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York</td>
</tr>
<tr>
	<td>Miami</td>
</tr>
<tr>
	<td>Chicago</td>
</tr>
<tr>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<h4 id="where">WHERE Clause</h4>

<p>When you retrieve information from database, there is more likely than not that you only want data that meet certain criteria. For example, you want to get the city name in the state of California. The <code>WHERE</code> clause can be used to filter all the records. The syntax looks like this:</p>

<pre><code>SELECT column_name, column_name ...
FROM table_name
WHERE column_name operators value;
</code></pre>

<p>The operators and value may not be very clear. Let&#8217;s use the same table to illustrate.</p>

<pre><code>SELECT City
FROM US City
WHERE State = 'CA'
</code></pre>

<p>The results will look like this:</p>

<table>
<colgroup>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
</tr>
</thead>

<tbody>
<tr>
	<td>San Francisco</td>
</tr>
<tr>
	<td>Los Angeles</td>
</tr>
<tr>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<p>The column used to filter, in this case, the &#8216;State&#8217; column does not need to be selected. I put <code>' '</code>around CA because CA is a string (text) not a number. To let SQL search for a string, we need to use syntax like this: &#8216;string&#8217;. If you are looking for a number, you don&#8217;t need to use the quotation mark. </p>

<p>Here are the list of all the operators:</p>

<ul>
<li><code>=</code>: Equal</li>
<li><code>&lt;&gt;</code> or <code>!=</code>: Not equal. Some version of SQL use <code>&lt;&gt;</code> while the other use <code>!=</code>.</li>
<li><code>&gt;</code>: Greater than</li>
<li><code>&lt;</code>: Less than</li>
<li><code>&gt;=</code>: Greater than or equal to</li>
<li><code>&lt;=</code>: Less than or equal to</li>
<li><code>BETWEEN</code>: between an inclusive range</li>
<li><code>LIKE</code>: Search for a pattern</li>
<li><code>IN</code>: Specify multiple possible values</li>
<li><code>REGEXP</code>: Search for a regular expression pattern</li>
</ul>

<p>Don&#8217;t worry if you do not really know how to use the last four operators. I will example them in detail.</p>

<h4 id="and-or">AND &amp; OR Operators</h4>

<p>Before diving into the operators listed above, let&#8217;s talk about the two basic operators <code>AND</code> &amp; <code>OR</code>. They are both used when there are more than one condition.</p>

<p><code>AND</code> display a record if all the conditions listing are true.
<code>OR</code> display a record if either one of the conditions is true.</p>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>For example, you are looking for &#8216;Springfield&#8217; in IL in US, but there are many &#8216;Springfield&#8217; in US. You can select the record using &#8216;AND&#8217;:</p>

<pre><code>SELECT City
FROM US City
WHERE City = 'Springfield' AND State = 'IL';
</code></pre>

<p>How about looking for cities that are either in Florida or Arizona?</p>

<pre><code>SELECT City
FROM US City
WHERE State = 'FL' OR State = 'AZ';
</code></pre>

<p>Of course you can combine <code>AND</code> &amp; <code>OR</code> together. To make it easier to read, add a parenthesis is a good idea.</p>

<pre><code>SELECT City
FROM US City
WHERE (City = 'Springfield') AND (State = 'IL' OR State = 'NY');
</code></pre>

<h4 id="between">BETWEEN Operator</h4>

<p><code>BETWEEN</code> operator selects values within a range. The values can be numbers, text or dates. They Syntax looks like this:</p>

<pre><code>SELECT column_name...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
</code></pre>

<p>For example:</p>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<pre><code>SELECT City
FROM US City
WHERE State BETWEEN 'AZ' AND 'CA';
</code></pre>

<p>Text ranges are based on alphabetical order. In the example above, the state between &#8216;AZ&#8217; and &#8216;CA&#8217; will be used to filter the values.</p>

<p>A more intuitive example:</p>

<p>&#8216;2016 US City Temperature&#8217;</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>20</td>
	<td>1/1</td>
</tr>
<tr>
	<td>Phoenix</td>
	<td>AZ</td>
	<td>70</td>
	<td>1/1</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<pre><code>SELECT City, Temperature
FROM 2016 US City Temperature
WHERE Temperature BETWEEN 50 AND 70;
</code></pre>

<p></p>

<h4 id="in">IN Operator</h4>

<p><code>IN</code> Operator filter values by specifying multiple values. The Syntax looks like this:</p>

<pre><code>SELECT column_name...
FROM table_name
WHERE column_name IN (value1, value2, ...);
</code></pre>

<p>When you want to select cities within certain states that is not within a range, you can write a statement like:</p>

<pre><code>SELECT City
FROM US City
WEHRE State IN ('AZ', 'IL', 'NY', 'CA');
</code></pre>

<p>The Cities in these four states will be selected. The order within &#8216;( )&#8217; does not matter.</p>

<h4 id="like">LIKE Operator</h4>

<p><code>LIKE</code> operator is used when you want to search for a pattern instead of a specific character. For example, you are looking for us city names start with &#8216;W&#8217;. The syntax looks like this:</p>

<pre><code>SELECT column_name...
FROM table_name
WHERE column_name LIKE pattern;
</code></pre>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>For example, to select cities start with letter &#8216;W&#8217;, you can write a statement like:</p>

<pre><code>SELECT City
FROM US City
WHERE City LIKE 'W%';
</code></pre>

<p>What does &#8216;%&#8217; mean? Well, it is a wildcard characters. These characters are used to search for a pattern within a table. Here are the list of all the wildcards used in SQL:</p>

<ul>
<li><code>%</code>: A substitute for 0 or more characters

<ul>
<li><code>W%</code> can match &#8216;Washington, D.C.&#8217; or &#8216;Waterbury&#8217;</li>
</ul></li>
<li><code>_</code>: A substitute for 1 character

<ul>
<li><code>_hicago</code> will match &#8216;Chicago&#8217;.</li>
</ul></li>
<li><code>[character_list]</code>: Sets and ranges of characters to match

<ul>
<li><code>[abc]%</code> can match &#8216;a%&#8217;, such as &#8216;Ann Arbor&#8217; or &#8216;b%&#8217; or &#8216;c%&#8217;.</li>
</ul></li>
<li><code>[^character_list]</code> | <code>[!character_list]</code>: Matches characters not within the brackets.

<ul>
<li><code>[\^abc]%</code> can match &#8216;d%&#8217;&#8230;</li>
</ul></li>
</ul>

<h4 id="regex">REGEXP Operator</h4>

<p>Did the above wildcards and examples remind you of something? Yeah! Regular Expression! It is much more powerful than LIKE operators, and we can use it in SQL. The syntax looks like:</p>

<pre><code>SELECT column_name 
FROM table_name
WHERE column_name REGEXP pattern;
</code></pre>

<p>In MySQL, <code>REGEXP</code> can be written as <code>RLIKE</code>. REGEXP is not case-sensitive, so &#8216;a&#8217; is the same with &#8216;A&#8217;. This is different from normal regex. All the details about regex can be found in my &#8216;What is Regular Expression&#8217; articles.</p>

<h4 id="limit">LIMIT Keyword</h4>

<p>The statements and operators above are about to select the data you are looking for. Next step is to clean up and play with the data you just selected. Here comes the keywords. They are used to organize the results.</p>

<p>First is a simple one: <code>LIMIT</code>. It is used to show the amount of results you are looking for.</p>

<pre><code>SELECT column_name
FROM table_name
WHERE column_name LIKE pattern
LIMIT number;
</code></pre>

<p>I used a random example after WHERE clause, you can use whatever you need after <code>WHERE</code>. <code>LIMIT number</code> will only show the number of results you are looking for. For example, <code>LIMIT 10</code> will show 10 results.</p>

<h4 id="select-top">SELECT TOP Clause # Only used in SQL Server and MS Access Syntax</h4>

<p><code>LIMIT</code> is useful when you are looking for a certain amount of results. If the data is too big and you are looking for the top 10%, it might not be very helpful. Here is a better way to specify the number of records:</p>

<pre><code>SELECT TOP number|percent column_name
FROM table_name;
</code></pre>

<h4 id="order-by">ORDER BY Keyword</h4>

<p>After selecting the data you are looking for, you may want to sort them. <code>ORDER BY</code> keyword is used to sort the result-set. The syntax looks like this:</p>

<pre><code>SELECT column_name...
FROM table_name
ORDER BY column_name ASC|DESC, column_name ASC|DESC;
</code></pre>

<p>The default is to sort the records in ascending order. Therefore, if you do not necessarily need to explicit write down &#8216;ASC&#8217;. To sort the records in a descending order, use &#8216;DESC&#8217; after <code>ORDER BY</code>. You can use multiple columns to sort the results.</p>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>Quick Example:</p>

<pre><code>SELECT City
FROM US City
ORDER BY State, City DESC;
</code></pre>

<h4 id="aliases">Aliases</h4>

<p>When you select a column or a table, it might be a good idea to rename them to make them more readable. Here is the Syntax:</p>

<p>To rename a column:
<code>
SELECT Column_name AS alias_name
FROM table_name;
</code></p>

<p>To rename a table:
<code>
SELECT Column_name
FROM table_name AS alias_name;
</code></p>

<p>For example:</p>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<pre><code>SELECT City AS IL City
FROM US City
WHERE State = 'IL';
</code></pre>

<p>The result will look like this:</p>

<table>
<colgroup>
<col/>
</colgroup>

<thead>
<tr>
	<th>IL City</th>
</tr>
</thead>

<tbody>
<tr>
	<td>Chicago</td>
</tr>
<tr>
	<td>Springfield</td>
</tr>
<tr>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<p>This simple example may not show the power of alias, since the name is clearly enough. Alias will be very helpful when we start to <code>JOIN</code> tables together that I will explain later.</p>

<h4 id="join">JOIN</h4>

<p>We used the US City table for all the previous examples. Right now, we just created another table with all the temperature information for each city. How to join the two tables together so that we can have the lists of cities and their daily temperatures? Here comes the <code>JOIN</code>. <code>JOIN</code> is used to combine rows from two or more tables. There are four different joins, and I will explain each of them. To illustrate, here are the two table examples to use. The code column of the two tables represent the same city. </p>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>Code</th>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>0001</td>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>0002</td>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>0003</td>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>9999</td>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>&#8216;US_City_Temperature&#8217;</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>Code</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>0001</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>0002</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<h5 id="inner-join">INNER JOIN （JOIN)</h5>

<p>This is the most common type of join, and it is very intuitive. An <code>INNER JOIN</code> returns all rows from multiple tables where the join condition is met. To join two tables together. There must be one column in common to combine two tables. Otherwise, system does not know which two rows should join together. Here is the syntax:</p>

<pre><code>SELECT column_name...
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
</code></pre>

<p>OR</p>

<pre><code>SELECT column_name...
FROM table1
JOIN table2
ON table1.column_name = table2.column_name;
</code></pre>

<p>Since this is the most common <code>JOIN</code>. We do not need to write down &#8216;INNER&#8217; specifically.</p>

<p>Here is the Venn Diagram to illustrate. I got this picture from W3school, which is a great website to learn SQL, HTML and so on.</p>

<figure>
<img src="https://www.w3schools.com/sql/img_innerjoin.gif" alt="W3School: InnerJoin Venn Diagram" />
<figcaption>W3School: InnerJoin Venn Diagram</figcaption>
</figure>

<p>In our example, we can combine the two tables by writing down:</p>

<pre><code>SELECT City, State, Temperature, Date
FROM US_City
(INNER) JOIN US_City_Temperature 
ON US_City.Code = US_City_Temperature.Code
</code></pre>

<p>The result will look like this:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<p>Since we combine the two tables based on the same code number, the system can combine the two tables correctly. Otherwise, the system may combine the temperature of Miami with Chicago, which will cause error. </p>

<p>Since this is <code>INNER JOIN</code>, the system will only choose city information that have the same code on both tables. If there are cities only show on one table, not both, this city&#8217;s information will be disregard when we combine the two tables.</p>

<h5 id="left-right-join">LEFT JOIN &amp; RIGHT JOIN</h5>

<p>Venn Diagram First:</p>

<figure>
<img src="https://www.w3schools.com/sql/img_leftjoin.gif" alt="W3School: LEFT JOIN" />
<figcaption>W3School: LEFT JOIN</figcaption>
</figure>

<figure>
<img src="https://www.w3schools.com/sql/img_rightjoin.gif" alt="W3School: RIGHT JOIN" />
<figcaption>W3School: RIGHT JOIN</figcaption>
</figure>

<p><code>LEFT JOIN</code> and <code>RIGHT JOIN</code> are basically the same thing. The only difference is the direction. <code>LEFT JOIN</code> returns all rows from the left table (table1) with the matching rows in the right table (table2). If there is no match on table2, it will return NULL, which means nothing. <code>RIGHT JOIN</code> is exactly the opposite. Here is the Syntax:</p>

<p><code>LEFT JOIN</code>:</p>

<pre><code>SELECT column_name(s)
FROM table1
LEFT (OUTER) JOIN table2
ON table1.column_name = table2.column_name;
</code></pre>

<p><code>RIGHT JOIN</code>:</p>

<pre><code>SELECT column_name(s)
FROM table1
RIGHT (OUTER) JOIN table2
ON table1.column_name = table2.column_name;
</code></pre>

<p>Whether you need <code>OUTER</code> or not depends on the database. </p>

<p>To illustrate, here are the two tables we use:</p>

<p>US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>Code</th>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>0002</td>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>0003</td>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>9999</td>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>&#8216;US_City_Temperature&#8217;</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>Code</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>0001</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>0002</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>9998</td>
	<td>79</td>
	<td>1/1/2016</td>
</tr>
</tbody>
</table>

<p>The table1 does not have city with code &#8216;0001&#8217; while table2 does not have city with code &#8216;9999&#8217;. When we left join the two table, the result will like this:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>null</td>
	<td>null</td>
</tr>
</tbody>
</table>

<p>The temperature and date information come from table2. Since there is no information in table2, the result will be null. Also, since New York City is missing in table1, even if there is data in table2, <code>LEFT JOIN</code> will not return results related to New York City. </p>

<p>The right join result will look like this:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>null</td>
	<td>null</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<p>Table2 has New York City information, so the <code>RIGHT JOIN</code> will return temperature information. Because table1 information is missing, the City and State Column will return &#8216;null&#8217;. Also, since table2 does not have information for Miami, <code>RIGHT JOIN</code> will not return any information for Miami even if it is in table1.</p>

<h5 id="full-join">FULL OUTER JOIN</h5>

<figure>
<img src="https://www.w3schools.com/sql/img_fulljoin.gif" alt="W3School: FULL OUTER JOIN" />
<figcaption>W3School: FULL OUTER JOIN</figcaption>
</figure>

<p>Venn Diagram shows very clear that <code>FULL OUTER JOIN</code> will return all rows from the left table (table1) and right table (table2). It combines the result of both <code>LEFT JOIN</code> and <code>RIGHT JOIN</code>. Here is the Syntax:</p>

<pre><code>SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name;
</code></pre>

<p>In our example, the result will look like this:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>null</td>
	<td>null</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>null</td>
	<td>null</td>
</tr>
</tbody>
</table>

<p>These are all four kinds of <code>JOIN</code>. Hope they can help you save a lot of time managing tables.</p>

<h4 id="union">UNION Operator</h4>

<p><code>JOIN</code> can combines different columns together and present a table that we want. <code>UNION</code>, on the other hand, will combines the rows together with the same column. It is used to combines the result of two or more <code>SELECT</code> statement. Here is the Syntax:</p>

<pre><code>SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2
</code></pre>

<p>And</p>

<pre><code>SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2
</code></pre>

<p>When using <code>UNION</code> operator, each <code>SELECT</code> statement must have the same amount of columns with same order. The columns must have similar data type.</p>

<p>The difference between <code>UNION</code> and <code>UNION ALL</code> is that <code>UNION</code> will return only distinct values while <code>UNION ALL</code> allow duplicate values. In reality, <code>UNION ALL</code> will operate faster than <code>UNION</code> since system does not need time to take out of duplicates values. </p>

<p>Here is the example. I have two tables. One is cities in US, and other is cities around the world, including cities in US. We can use <code>UNION</code> to get a table about unique cities around the world. We can use <code>UNION ALL</code> to get a table about cities around the world with duplicate US cities.</p>

<p>&#8216;US City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>&#8216;World City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>Berlin</td>
	<td>Germany</td>
</tr>
<tr>
	<td>London</td>
	<td>UK</td>
</tr>
<tr>
	<td>Beijing</td>
	<td>China</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>To combine them with only distinct value:</p>

<pre><code>SELECT City, Country FROM US City
UNION
SELECT City, Country FROM World City
</code></pre>

<p>The result will look like this:</p>

<table>
<colgroup>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Berlin</td>
	<td>Germany</td>
</tr>
<tr>
	<td>London</td>
	<td>UK</td>
</tr>
<tr>
	<td>Beijing</td>
	<td>China</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<p>If we use <code>UNION ALL</code>, the result will look like this:</p>

<table>
<colgroup>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Berlin</td>
	<td>Germany</td>
</tr>
<tr>
	<td>London</td>
	<td>UK</td>
</tr>
<tr>
	<td>Beijing</td>
	<td>China</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>Notice there are two &#8216;Chicago&#8217; since <code>UNION ALL</code> allows duplicate values. </p>

<h4 id="null">NULL Values</h4>

<p>When we use <code>LEFT JOIN</code> and <code>RIGHT JOIN</code>, it is possible to get a lot of NULL values. What is NULL values exactly? In short, NULL value is a field with no value in a table. </p>

<p>There is a way to test whether a table has NULL values. Since NULL values are different from other values, we cannot test with normal comparison operators like =, &lt;&gt;. Instead, we need to use <code>IS NULL</code> or <code>IS NOT NULL</code>.</p>

<p>For example, here is a table with NULL value in it:</p>

<p>&#8216;Temperature&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>null</td>
	<td>null</td>
	<td>50</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Orlando</td>
	<td>FL</td>
	<td>70</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>null</td>
	<td>null</td>
</tr>
</tbody>
</table>

<p>To select cities with both city name and temperature, we can use something like this:</p>

<pre><code>SELECT City, State, Temperature, Date
FROM Temperature
WHERE (City IS NOT NULL) AND (Temperature IS NOT NULL);
</code></pre>

<p>Result will be something like:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Temperature</th>
	<th>Date</th>
</tr>
</thead>

<tbody>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>43</td>
	<td>1/1/2016</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Orlando</td>
	<td>FL</td>
	<td>70</td>
	<td>1/1/2016</td>
</tr>
</tbody>
</table>

<p>Rows with NULL values will not be selected.</p>

<h4 id="aggregate-function">Aggregate Functions</h4>

<p>In SQL, there are many built-in functions to help perform calculations on Data. One type is aggregate functions. By being input values from a column, they can return a single value. This is why they are called &#8216;aggregate&#8217; functions.</p>

<p>Here are the list of some commonly used aggregate functions. They can be used the same way as used in Excel.</p>

<ul>
<li>AVG(): Return the average value</li>
<li>COUNT(): Returns the number of rows</li>
<li>FIRST(): Returns the first value</li>
<li>LAST(): Returns the last value</li>
<li>MAX(): Returns the largest value</li>
<li>MIN(): Returns the smallest value</li>
<li>ROUND(): Rounds a numeric field to the number of decimals specified</li>
<li>SUM(): Returns the sum</li>
</ul>

<h4 id="group-by">GROUP BY Statement</h4>

<p><code>GROUP BY</code> statement is used with an aggregate functions mentioned above to group the result-set by columns. Here is the Syntax:</p>

<pre><code>SELECT column_name, aggregate_function(column_name)
FROM table_name
WHERE column_name operator value
GROUP BY column_name;
</code></pre>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>To calculate how many cities in each state, we can write something like this:</p>

<pre><code>SELECT State, count(City) AS Number_of_City
FROM US_City
GROUP BY State
ORDER BY State;
</code></pre>

<p>The result will like this (I made up the number!):</p>

<table>
<colgroup>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>State</th>
	<th>Number_of_City</th>
</tr>
</thead>

<tbody>
<tr>
	<td>AL</td>
	<td>45087</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>HI</td>
	<td>2944</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
</tbody>
</table>

<h4 id="having">HAVING Clause</h4>

<p>After learning about aggregate functions, we can select data that based on aggregate value. However, <code>WHERE</code> clause cannot be used with aggregate functions. We need to use <code>HAVING</code> clause to achieve this. Here is the Syntax:</p>

<pre><code>SELECT column_name, aggregate_function(column_name)
FROM table_name
WHERE column_name operator value
GROUP BY column_name
HAVING aggregate_function(column_name) operator value;
</code></pre>

<p>&#8216;US_City&#8217;:</p>

<table>
<colgroup>
<col/>
<col/>
<col/>
<col/>
</colgroup>

<thead>
<tr>
	<th>City</th>
	<th>State</th>
	<th>Country</th>
</tr>
</thead>

<tbody>
<tr>
	<td>New York City</td>
	<td>NY</td>
	<td>US</td>
</tr>
<tr>
	<td>Chicago</td>
	<td>IL</td>
	<td>US</td>
</tr>
<tr>
	<td>San Francisco</td>
	<td>CA</td>
	<td>US</td>
</tr>
<tr>
	<td>&#8230;</td>
	<td>&#8230;</td>
	<td>&#8230;</td>
</tr>
<tr>
	<td>Miami</td>
	<td>FL</td>
	<td>US</td>
</tr>
</tbody>
</table>

<p>To select state that has more than 5,000 cities, we can write something like:</p>

<pre><code>SELECT State, COUNT(Cities) AS Number_of_City
FROM US_City
GROUP BY State
HAVING COUNT(Cities) &gt; 5000
ORDER BY State;
</code></pre>

<h4 id="comments">Comments</h4>

<p>When we write down the queries to get all the data, we may want to add comments to help people understand. Comments will not be execute by system. Comments can also be used to prevent execution when testing SQL statements. </p>

<p>Syntax for single line comments:</p>

<pre><code>-- Select All (This will not be executed, just a comment)
SELECT * FROM US_City; (This will be executed since it is not the same line with --)
</code></pre>

<p>Syntax for Multi-line comments:</p>

<pre><code>/*This will not be executed.
This is just a comment.
Still a comment.
Final comment.*/
SELECT * FROM US_City; (This will be executed)
</code></pre>

<h3 id="resources">Resources</h3>

<p>The above are the basics of SQL. There are more functions within SQL to make it more powerful. Here are some documentations to refer for future uses:</p>

<ul>
<li><a href="https://www.w3schools.com/sql/sql_quickref.asp">W3School</a></li>
<li><a href="https://dev.mysql.com/doc/">MySQL</a></li>
<li><a href="https://docs.oracle.com/cd/B19306_01/server.102/b14200/toc.htm">Oracle SQL References</a></li>
</ul>
