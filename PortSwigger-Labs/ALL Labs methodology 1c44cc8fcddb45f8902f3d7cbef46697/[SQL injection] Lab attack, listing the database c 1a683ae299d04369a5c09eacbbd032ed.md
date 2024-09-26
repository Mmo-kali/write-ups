# [SQL injection] Lab: attack, listing the database contents on non-Oracle databaseThis lab is apart of my journey towards my BSCP (1)

---

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled.png)

lets first visit the site without a proxy and we want to map the functionality of the site out. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%201.png)

now that we can see the category filter lets like on them with the proxy and determine the number of columns with in the original query. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%202.png)

now we know there is 2 columns within the original query. now lets figure out the database version. i tried using the ‘#’ as a comment when trying my different queries, and it gave me a error so i know it’s not MySQL. let check if it MicrosoftDB with ‘@@version’  that also gave me a error lets try version() in for PostegresSQL

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%203.png)

now lets use the information_schema to get information about the database  

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%204.png)

by injecting this query we’re able to get all the table names from the information_schema.tables, 

now lets find possible tables that contain username and password: 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%205.png)

now lets find the column name: 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%206.png)

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%207.png)

now that we have the column names lets select all data from those 2 columns to get user name and passwords 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%208.png)

I concatenated the 2 string columns to be outputted into the single column of string type with ~ as the delimiter. 

now lets login 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%201a683ae299d04369a5c09eacbbd032ed/Untitled%209.png)

and there we go we solved this lab!