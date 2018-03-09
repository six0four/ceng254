# CENG 254

## Table of Contents
1. [Lab 00](#lab-00)
2. [Lab 01](#lab-01)
3. [Lab 02](#lab-02)
4. [Lab 03](#lab-03)
5. [Lab 04](#lab-04)
6. [Lab 05](#lab-05)
7. [Lab 06](#lab-06)
8. [Lab 07](#lab-07)
9. [Lab 08](#lab-08)
10. [Lab 09](#lab-09)

## Lab 00

### Part 1 (/0.5)
1. Use an ssh terminal such as <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">PuTTY</a> to connect to apollo.humber.ca
2. Once logged in type:
```
[n12345678@apollo ~]$ sqlplus
```
3. enter your username and password.   
4. next change your password (and record it) by entering the following and following the prompts:
```
SQL> password
```
4. Show your SQL prompt to your professor.
5. to exit type:
```
SQL> quit 
```

### Part 2 (/1.0)
1. Use <a href="http://www.oracle.com/technetwork/developer-tools/sql-developer/downloads/index.html">Oracle's SQL Developer</a>   
2. From the Windows start menu Run SQL developer  
3. Confirm the dialogs   
4. On the left hand menu click the green plus button.  
5. On the form that pops up fill in the information that follows:
```
Connection Name: choose a name (e.g. apollo_oracle)
Username: your humber id (e.g. n12345678)
Password: your password as you chose above
Hostname: apollo.humber.ca
Port: 1521
SID: msit
```
6. Select the TEST button to verify.   
7. Select connect.
8. Go to <a href="http://www.oraclesqlbyexample.com/download-the-sample-database.html">Oracle SQL by Example/Alice Rischert</a>.
9. Download the scripts.exe​ file.
10. After you download the file, double click on scripts.exe file and unzip the files to the C:\guest\schemasetup directory.
11. In SQL Developer Click File Open.
12. Click the Browse button to locate in the C:\guest\schemasetup directory the script named createStudent.sql
13. Open the file, which brings it into the worksheet.
14. Click the Run Script icon or F5 to run the script.
15. After the script completes (approximately 3-5 minutes), it will show a list of
counts representing the number of rows it created for each table. Compare
that list on screen with the following list. The two lists should match. If you
used SQL Developer, you may need to scroll all the way to the bottom of the
screen to see the result.
```
Count of COURSE Table: 30
Count of ENROLLMENT Table: 226
Count of GRADE Table: 2004
Count of GRADE_CONVERSION Table: 15
Count of GRADE_TYPE Table: 6
Count of GRADE_TYPE_WEIGHT Table: 300
Count of INSTRUCTOR Table: 10
Count of SECTION Table: 78
Count of STUDENT Table: 268
Count of ZIPCODE Table: 227
```
16. Click the Browse button to locate in the C:\guest\schemasetup directory the script named sql_book_add_tables.sql
17. Open the file, which brings it into the worksheet.
18. Click the Run Script icon or F5 to run the script.
19. Select your apollo_oracle connection tab.
20. Type SELECT * FROM COURSE
21. Click the Run Script icon or F5 to run the script.
22. Show the output of the command in SQL Developer to your professor.

### Part 3 (/0.5)
1. [Login to Lynda.com](https://login.humber.ca/cas/login?service=https://www.lynda.com/portal/humber)  
    1. Visit lynda.com website
    2. Click 'Sign In' button
    3. Click Organization Login tab (NOT Individual Login)
    4. Enter 'www.humber.ca' under organization's URL
    5. Click 'Go' and you will be redirected to login.humber.ca
    6. Enter your Humber username and password and click 'LOGIN' button
    7. You will be redirected back to Lynda.com with full course access to create your own user name.
    8. Feel free to register via Toronto Public Library instead such that your access is not cut off when you graduate.
2. Go to [Programming Foundations: Databases](https://www.lynda.com/Programming-Foundations-tutorials/Foundations-Programming-Databases/412845-2.html) and show that the "Welcome" video from the Introduction has been marked viewed (perhaps without sound) your professor.
3. Friday's quiz will be based on Chapter 1 Understanding Databases and Chapter 2 Database Fundamentals. It is only about half an hour of videos and you are expected to spend about an hour outside of class for every hour in class.
4. Extra consideration: email me any file I/O code you wrote in CENG 212 Programming Techniques in Java.

## Lab 01
Assignment #1

## Lab 02
Assignment #2

## Lab 03
Assignment #3

## Lab 04
Assignment #4

## Lab 05
Assignment #5

## Lab 06
Assignment #6

## Lab 07
Assignment #7

## Lab 08
Assignment #8

## Lab 09
More JDBC/SQLite to come.

## Lab 10
1. Use an ssh terminal such as <a href="https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html">PuTTY</a> to connect to munro.humber.ca
2. Once logged in type:
```
[n12345678@apollo ~]$ cd public_html
```
3. Create the directory:
```
/home/students/n12345678/public_html/ceng254
```
3. Set appropriate permissions.
4. Change to that directory and create an index.jsp again with appropriate permissions.
5. Complete Learning Java Applications Chapter 6 in the lab using this environment by using the following instead:
```
<!-- will be hosted at http://munro.humber.ca/~n12345678/ceng254/index.jsp -->
<%@page import = "java.sql.*" %>
<%@page contentType="text/html" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title>JSP Page</title>
    </head>
    <body>
        <h1>Hello World!</h1>
        <p>
        <ul>
         <%
                Connection c = DriverManager.getConnection("jdbc:oracle:thin:@apollo.humber.ca:1521:msit" ,"n12345678", "ORACLE");
                Statement s = c.createStatement();

                String query = ("SELECT * FROM STUDENT");
                ResultSet result = s.executeQuery(query);
                while (result.next()) {
                        %>
                        <li><%= result.getString("first_name") %></li>
                        <%
                }
                c.close();
          %>
        <ul>
        </p>
    </body>
</html>
```
6. This content will be part of Friday's quiz.
