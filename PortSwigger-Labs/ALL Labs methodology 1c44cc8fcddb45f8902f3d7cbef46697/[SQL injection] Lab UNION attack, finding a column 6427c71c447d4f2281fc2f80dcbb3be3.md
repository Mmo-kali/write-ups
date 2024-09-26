# [SQL injection] Lab: UNION attack, finding a column containing text (1)

---

This lab is apart of my journey towards the Burp suite certified professional/ 

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled.png)

So my first step in all my labs is to visit the site without and tools or proxy, to map out the application and to find it’s functionality 

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%201.png)

The site seems to be some type of shopping website with different categories that we can use as filters, these maybe where we can exploit this database. 

Lets turn the proxy on and see how the application function when i select one of those categories. 

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%202.png)

as we can see similarly to the previous lab this database is passing the parameter for it’s query directly from the Http request in a unsafe way so we can possibly exploit this. 

Since we want to get data from other table be need to use a SQL injection UNION attack. But to do this attack we need 2 conditions to be met. 

**Condition 1: Injected query must have same amount of Columns as the original**

**Condition 2: the Injected query columns but be of the same type as the columns we are injection to get data from.** 

In order to find the number of column in the table there are 2 methods. Method 1:  Using ORDER BY and index the column until we get an error or Method 2: using SELECT NULL from dual table in oracle followed by two dashes to show the comment sequence.         

 Lets try and use the 

```jsx
' ORDER BY 1--
```

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%203.png)

We got up to 3 lets try 4

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%204.png)

So we have 3 columns in total lets figure out the column types. 

so now lets check for the column type, usually the data we are trying to get is of string type so lets use the ‘a’ to see which columns give an error. 

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%205.png)

First column gave an error 

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%206.png)

the second column doesn’t give me an issue so lets not query for the string that was given at the beginning of the lab. 

so lets swap ‘a’ for ‘DrRGRx’

and there we go lab solved

![Untitled](%5BSQL%20injection%5D%20Lab%20UNION%20attack,%20finding%20a%20column%206427c71c447d4f2281fc2f80dcbb3be3/Untitled%207.png)