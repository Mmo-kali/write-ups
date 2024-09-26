# [SQL injection] UNION attack, retrieving data from other tables (1)

This lab is apart of my journey BSCP journey 

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled.png)

so first thing i do is visit the site without a proxy on to map out the application and it functionality 

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled%201.png)

it is a shopping platform again with a My account button in top right but also category filters, lets turn on the proxy and see the requests that are being sent to the back end

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled%202.png)

so this looks like a possible sql vulnerability and since the lab mentioned SQL Injection union attacklet me start off by testing for the number of columns within the database. 

to find the number of columns i will use ‘ORDER BY [COLUMN INDEX] — until i get a error which signifies the number of columns in the tables. 

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled%203.png)

This tells me that there is two columns lets check the column types, by supplying a null and a string character. 

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled%204.png)

since this work it mean that both columns are of compatible type with string. 

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled%205.png)

and there we have it we solved the lab 

![Untitled](%5BSQL%20injection%5D%20UNION%20attack,%20retrieving%20data%20from%2094817bafc8844640ba7e6c5fb5eff37b/Untitled%206.png)