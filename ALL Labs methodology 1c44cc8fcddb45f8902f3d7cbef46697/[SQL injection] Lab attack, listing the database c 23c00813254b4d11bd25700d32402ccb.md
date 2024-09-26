# [SQL injection] Lab: attack, listing the database contents on Oracle (1)

---

This lab is apart of my journey towards my BSCP 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled.png)

lets visiting the site with no proxy, lets just map out the web app to get idea of it’s functionality. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%201.png)

we can see it is a shopping application. with category filters at the top lets click on one of them with the proxy on. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%202.png)

now we know there is 2 columns. also for Oracle DB we always need a from table so we can use the built in table dual. 

now lets see which columns support a str type for our sql injection union attack. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%203.png)

we can see that the first column support str type. 

so now lets get tables names. in Oracle we dont use information_schema for DB info rather we have a tale called all_tables. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%204.png)

now that we found the table with possible username and password lets find the column names. 

now lets user the all_tab_columns to get columns name: 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%205.png)

perfect now lets do select on that USERS table and concatenate the 2 string columns into one output. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%206.png)

Perfect so now we have password lets login. 

![Untitled](%5BSQL%20injection%5D%20Lab%20attack,%20listing%20the%20database%20c%2023c00813254b4d11bd25700d32402ccb/Untitled%207.png)

perfect and there we have it another lab solved.