# [SQL injection] Lab:  querying the database type and version on Oracle (1)

This lab is part of my journey toward the BSCP cert 

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled.png)

so when starting lab lets explore site to do some basic recon on the functionality and how the site works

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled%201.png)

so it’s a shopping website with category filters, that can possibly be exploited let’s click on one with the proxy on in burp suite to see what request is being sent. 

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled%202.png)

perfect so looks like this application is pass the parameter from the http request to the query in a unsafe way we can possibly exploit this. 

my first thought and also because the the lab mentioned it was using a union sql injection attack since it is used for being able to retrieve information from other tables in the Database. 

**NOTE:** another thing to keep in mind is that to be able to retrieve the database version that requires for us to  give a provider-specific query since different type of DB providers have different solutions for getting the data base version. 

in oracle it’s `SELECT * FROM v$version`

so for out union attack lets inject this: 

```sql
'UNION SELECT * FROM v$version -- to comment out the end...

```

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled%203.png)

so the second column is of string type

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled%204.png)

so by checking the column type we can now retrieve data from v$version, 

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled%205.png)

and there we have it we solved that lab 

![Untitled](%5BSQL%20injection%5D%20Lab%20querying%20the%20database%20type%20and%20412125f13f30423ba774601261cda338/Untitled%206.png)