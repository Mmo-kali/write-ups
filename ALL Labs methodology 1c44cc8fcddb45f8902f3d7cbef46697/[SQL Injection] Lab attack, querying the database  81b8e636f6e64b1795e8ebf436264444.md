# [SQL Injection] Lab: attack, querying the database type and version on MySQL and Microsoft (1)

---

This lab is apart of my journey towards getting BSCP.

![Untitled](%5BSQL%20Injection%5D%20Lab%20attack,%20querying%20the%20database%20%2081b8e636f6e64b1795e8ebf436264444/Untitled.png)

To begin lets visit the site with out a proxy to map out the functionality of the site. and see how it’s designed. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20attack,%20querying%20the%20database%20%2081b8e636f6e64b1795e8ebf436264444/Untitled%201.png)

so the site is some time of shop that has been designed with category filter buttons that the top of the page. 

lets click on some of those filters and see the request that is being sent. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20attack,%20querying%20the%20database%20%2081b8e636f6e64b1795e8ebf436264444/Untitled%202.png)

as we can see the parameter for the category is being passed directly into the query in a insecure way lets check and see if we could possibly do a UNION attack by determining the number of columns that the original query is returning. 

in MySQL a alternative way to leave a comment is with the # rather then the double dash comment sequence, when doing a double dash i always am getting a 500, but when doing with the ‘#’ im able to sucessfully get the number of columns by using ORDER BY 

![Untitled](%5BSQL%20Injection%5D%20Lab%20attack,%20querying%20the%20database%20%2081b8e636f6e64b1795e8ebf436264444/Untitled%203.png)

This means that there is two columns so now lets figure out the columns types. since when doing SQL injection Union attack we need a column of useful type and since we will be getting string data. 

to get the column type i will supply a string value into one of the columns to see if it give me a error since that column is not compatible with the string type. 

to get databse version in microsoft and MySQL we can use @@version 

![Untitled](%5BSQL%20Injection%5D%20Lab%20attack,%20querying%20the%20database%20%2081b8e636f6e64b1795e8ebf436264444/Untitled%204.png)

And there we are we solved the lab. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20attack,%20querying%20the%20database%20%2081b8e636f6e64b1795e8ebf436264444/Untitled%205.png)