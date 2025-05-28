**Task 2 - Databases 101**

*Q1: What type of database should you consider using if the data you're going to be storing will vary greatly in its format?*

A: **Non-relational** databases store data in a non-tabular format. This is used for instances such as asked in the question above.

*Q2: What type of database should you consider using if the data you're going to be storing will reliably be in the same structured format?*

A: **Relational** databases store data that is typically related to each other. It is usually stored in tables and is formatted as such.

*Q3: In our example, once a record of a book is inserted into our "Books" table, it would be represented as a ___ in that table?*

![alt text](<noah-repos/Images/sql-fig1.png>)

A: In the example, once a book is inserted into the books table, it would be represented as a **row** in the table.

*Q4: Which type of key provides a link from one table to another?*

A: A **Foreign Key**, as the name implies, will link one table to another table; meaning the data itself is foreign and is referring to another table.

*Q5: Which type of key ensures a record is unique within a table?*

A: A **Primary Key** ensures that a record is unique in a given database table.

**Task 3 - SQL**

*Q1: What serves as an interface between a database and an end user?*

A: **DBMS or Database Management Systems** serve as an interface between the end user and the database itself.

*Q2: What query language can be used to interact with a relational database?*

A: **SQL, or Structured Query Language** is what is used to interact with a relational database.

**Task 4 - Database and Table Statements**

*Q1: Using the statement you've learned to list all databases, it should reveal a database with a flag for a name; what is it?*

A: First, we must log into SQL. This can be done via the command *mysql -u USER -p PASSWORD*.
Once that is done, to show databases, we enter the following command into SQL: *SHOW DATABASES;*. The semicolon is **EXTREMELY** important, as without it, it is improper syntax, and you will error out.

![alt text](<noah-repos/Images/sql-fig2.png>)

We can see that the flag we are looking for is the first database shown.

*Q2: In the list of available databases, you should also see the **task_4_db** database. Set this as your active database and list all tables in this database; what is the flag present there?*

A:  To begin, we must select *task_4_db* as our active database. To do this, we need to tell SQL to do so: *USE task_4_db;* is the command. Once we have the database active, we can now look at the tables in the database: *SHOW TABLES;*.

![alt text](<noah-repos/Images/sql-fig3.png>)

**Task 5 - CRUD Operations**

*Q1: Using the **tools_db** database, what is the name of the tool in the **hacking_tools** table that can be used to perform man-in-the-middle attacks on wireless networks?*

A: Using the same initial steps we took in task 4, we can navigate over to the **tools_db** database. From there, this is where it differs. When we show the tables, it doesn't show us anything except the name of the only table in the database itself. Let's see what's in the actual table. We do this through a **Read Operation** (AKA SELECT). This is accomplished via the following command: *SELECT (asterisk) FROM **TABLENAME***. Once we are viewing the table, we will have our answer: 

![alt text](<noah-repos/Images/sql-fig4.png>)

*Q2: Using the **tools_db** databse, what is the shared category for both **USB Rubber Ducky** and **Bash Bunny**?*

A: As seen in the table above, both items are categorized the same. Both of these devices are used in USB-based attacks, and are categorized as such.

**Task 6 - Clauses**

*Q1: Using the **tools_db** database, what is the total number of distinct categories in the **hacking_tools** table?*

A: To answer this question, we are going to be using the **DISTINCT** clause. This will directly tell us how many unique categories there are by looking at and comparing the rows. We do this via the following: *SELECT DISTINCT category FROM hacking_tools;*

![alt text](<noah-repos/Images/sql-fig5.png>)

From the image, we can see that our answer is **Six**.

*Q2: Using the **tools_db** database, what is the first tool (by name) in ascending order from the **hacking_tools** table?*

A: For the answer, we must use the **ORDER BY** clause, with the **ASC** modifier. This tells SQL to list the rows in ascending order. Let's run the query: 
**SELECT (asterisk)
FROM hacking_tools
ORDER BY name ASC**.
The table will appear alphabetically, and we can see that **Bash Bunny** is our answer.

![alt text](<noah-repos/Images/sql-fig6.png>)

*Q3: Using the **tools_db** database, what is the first tool (by name) in descending order from the **hacking_tools** table?*

A: This answer will be very similar to the last. It is basically the same command with a different modified in the **ORDER BY** line. Instead of **ASC**, we will be using **DESC**. The result is as follows:

![alt text](<noah-repos/Images/sql-fig7.png>)

We can see that our answer is Wi-Fi Pineapple.

**Task 7 - Operators**

*Q1: Using the **tools_db** database, which tool falls under the **Multi-tool** category and is useful for **pentesters** and **geeks**?*

A: Using the **equals** operator, we can find which hacking tool is considered a "Multi-tool". This can be done through the following command:
**SELECT (asterisk)
FROM hacking_tools
WHERE category = "Multi-tool"**
This allows us to just search for the "Mutli-tool" category in the database.

![alt text](<noah-repos/Images/sql-fig8.png>)

As seen in the image, our answer is the **Flipper Zero**.

*Q2: Using the **toold_db** database, what is the category of tools with an amount **greater than** or **equal** to **300**?*

A: For this answer, we are going to need a different operator. Let's fire off the command:
**SELECT (asterisk)
FROM hacking_tools
WHERE amount >= "300";**

Upon running the command, we see two results; both from the same category:

![alt text](<noah-repos/Images/sql-fig9.png>)


This makes our answer **RFID Cloning**.

*Q3: Using the **tools_db** database, which tool falls under the **Network Intelligence** category with an amount **less than 100**?*

A: This is where it gets a little more complicated. We need another snippet in our query to apply some more logic.
Let's do it:

**SELECT (asterisk)
FROM hacking_tools
WHERE category = "Network Intelligence" AND amount < "100";**

We needed to add an **AND** operator to our logic in SQL to have both requirements be present in our query. Let's see the results:

![alt text](<noah-repos/Images/sql-fig10.png>)

**LAN Turtle** is our answer.

**TASK 8 - Functions**

*Q1: Using the **tools_db** database, what is the tool with the longest name based on character length?*

A: Using the **LENGTH()** function, we can determine which name has the most characters. We can see from the image below the most is 16 characters:

![alt text](<noah-repos/Images/sql-fig11.png>)

We can see that row 4 has 16 characters. We could get extremely fancy with it. Let's do it:

![alt text](<noah-repos/Images/sql-fig12.png>)

From the image above, we ordered our hacking tools by character length in their names, in descending order. Thus, our answer is **USB Rubber Ducky**


*Q2: Using the **tools_db** database, what is the total sum of all tools?*

A: What the question is really asking for is the sum of the **amount** column. So, let's do just that. 

![alt text](<noah-repos/Images/sql-fig13.png>)

The snippet above shows SQL taking the amount column and displaying the sum of the prices. Our answer is **1444**.

*Q3: Using the **tools_db** database, what are the tool names where the amount does not end in **0**, and **group** the tool names **concatenated** by "&".*

A: To begin, we are going to use the GROUP_CONCAT function to concatenate an & as our separator. This is done by the command **GROUP_CONCAT(name, SEPARATOR " & ");**
Then we need to specify it is from hacking_tools, and then to make sure it is not ending in a zero (even number!) we make sure that there is no remainder with MOD 0.

![alt text](<noah-repos/Images/sql-fig14.png>)

**Thanks for reading my walkthrough!**
