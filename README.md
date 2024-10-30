These functions operate on a set of values and return a single result.
1.aggregate functions
Function	Description	Example
SUM()	Returns the sum of a numeric column.	SELECT SUM(Salary) FROM Employees;
AVG()	Returns the average value of a numeric column.	SELECT AVG(Salary) FROM Employees;
COUNT()	Counts the number of rows.	SELECT COUNT(*) FROM Employees;
MIN()	Returns the smallest value in a column.	SELECT MIN(Salary) FROM Employees;
MAX()	Returns the largest value in a column.	SELECT MAX(Salary) FROM Employees;
  
2.string functions
UPPER()	Converts a string to uppercase.	SELECT UPPER(Name) FROM Employees;
LOWER()	Converts a string to lowercase.	SELECT LOWER(Name) FROM Employees;
LENGTH()	Returns the length of a string.	SELECT LENGTH(Name) FROM Employees;
TRIM()	Removes leading and trailing spaces.	SELECT TRIM(' Hello ');
SUBSTRING()	Extracts a substring from a string.	SELECT SUBSTRING(Name, 1, 3) FROM Employees;
CONCAT()	Concatenates two or more strings.	SELECT CONCAT(FirstName, ' ', LastName) FROM Employees;
REPLACE()	Replaces occurrences of a substring.	SELECT REPLACE(Name, 'John', 'Johnny') FROM Employees;

3.date functions
URRENT_DATE()	Returns the current date.	SELECT CURRENT_DATE();
CURRENT_TIME()	Returns the current time.	SELECT CURRENT_TIME();
NOW()	Returns the current date and time.	SELECT NOW();
DATE_ADD()	Adds a specified time to a date.	SELECT DATE_ADD(CURRENT_DATE(), INTERVAL 7 DAY);
DATEDIFF()	Returns the difference between two dates.	SELECT DATEDIFF('2024-12-31', '2024-01-01');
EXTRACT()	Extracts a specific part (year, month, etc.) from a date.	SELECT EXTRACT(YEAR FROM CURRENT_DATE());

4.Mathematical functions
ABS()	Returns the absolute value.	SELECT ABS(-10);
ROUND()	Rounds a number to the nearest integer.	SELECT ROUND(3.14159, 2);
CEIL()	Rounds a number up to the nearest integer.	SELECT CEIL(3.14);
FLOOR()	Rounds a number down to the nearest integer.	SELECT FLOOR(3.14);
MOD()	Returns the remainder of a division.	SELECT MOD(10, 3);
POWER()	Returns a number raised to the power of another.	SELECT POWER(2, 3);
SQRT()	Returns the square root of a number.	SELECT SQRT(16);

5.window functiona
ROW_NUMBER()	Assigns a unique number to each row.	SELECT Name, ROW_NUMBER() OVER (ORDER BY Name) AS RowNum FROM Employees;
RANK()	Assigns a rank to each row, with gaps for ties.	SELECT Name, RANK() OVER (ORDER BY Salary DESC) AS Rank FROM Employees;
DENSE_RANK()	Similar to RANK(), but without gaps for ties.	SELECT Name, DENSE_RANK() OVER (ORDER BY Salary DESC) FROM Employees;
NTILE()	Divides rows into a specified number of groups.	SELECT Name, NTILE(3) OVER (ORDER BY Salary DESC) FROM Employees;
LEAD()	Accesses the value of a subsequent row.	SELECT Name, Salary, LEAD(Salary) OVER (ORDER BY Salary) FROM Employees;
LAG()	Accesses the value of a previous row.	SELECT Name, Salary, LAG(Salary) OVER (ORDER BY Salary) FROM Employees;

6.Conditional functions
Conditional functions allow for decision-making in SQL queries.
Function	Description	Example
CASE	Returns different results based on conditions.	SELECT Name, CASE WHEN Salary > 50000 THEN 'High' ELSE 'Low' END FROM Employees;
IF()	Evaluates a condition and returns a value.	SELECT IF(Salary > 50000, 'High', 'Low') FROM Employees;
COALESCE()	Returns the first non-null value.	SELECT COALESCE(NULL, NULL, 'Default');
NULLIF()	Returns NULL if two values are equal.	SELECT NULLIF(Salary, 0) FROM Employees;

7. Conversion Functions
These functions convert data from one type to another.
Function	Description	Example
CAST()	Converts a value to a specified data type.	SELECT CAST(123.45 AS INT);
CONVERT()	Converts a value to a specified data type.	SELECT CONVERT(INT, '123');

8. JSON Functions (in modern SQL databases)
These functions help work with JSON data types.
Function	Description	Example
JSON_EXTRACT()	Extracts data from a JSON string.	SELECT JSON_EXTRACT('{"name": "John"}', '$.name');
JSON_OBJECT()	Creates a JSON object.	SELECT JSON_OBJECT('name', 'John', 'age', 30);
JSON_ARRAY()	Creates a JSON array.	SELECT JSON_ARRAY('John', 30);

9. Bitwise Functions
These functions perform bitwise operations.
Function	Description	Example
BIT_AND()	Returns the bitwise AND of all values.	SELECT BIT_AND(5, 3);
BIT_OR()	Returns the bitwise OR of all values.	SELECT BIT_OR(5, 3);
BIT_XOR()	Returns the bitwise XOR of all values.	SELECT BIT_XOR(5, 3);
10. Security and Hashing Functions
Some SQL databases provide hashing functions for security.

10.security and hashing
Function	Description	Example
MD5()	Returns the MD5 hash of a string.	SELECT MD5('password');
SHA1()	Returns the SHA-1 hash of a string.	SELECT SHA1('password');
PASSWORD()	Returns the encrypted version of a string.	SELECT PASSWORD('my_secret');



