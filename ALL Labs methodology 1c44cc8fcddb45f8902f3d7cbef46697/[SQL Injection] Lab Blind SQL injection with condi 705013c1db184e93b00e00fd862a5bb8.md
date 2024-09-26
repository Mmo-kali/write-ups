# [SQL Injection] Lab: Blind SQL injection with conditional responses (1)

---

This is apart of the BSCP path 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled.png)

first lets visit the site with the proxy off to see the functionality of the site since im going to be exploiting this web app to get a username and password im going to be going straight to the login page. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%201.png)

so lets go to the login page, one thing i noticed is a message that appears On the page saying welcome back. 

now I am  curious as to how it is displaying that welcome back message so lets turn on the proxy and look at the request that is being sent. 

so when trying to login with 2 test values this is the request: 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%202.png)

what is this ‘*TrackingID*’? lets set this condition to false to see how the website behaves so first lets send to to repeater then Im going to grep the response and turn on auto-scroll to position of match so whenever the “Welcome back!” message appears i will know instantly.

well since this is a Web-app that isn’t returning and errors or results of the query back to the application for use to see this is a Blind SQL injection attack. This requires use of more advanced techniques to be able to extract data. 

**How do i set the TrackingID to false?** 

- well i could inject a Boolean condition that could make whatever the result of the original query is always true or always false.

```sql
'+AND+'1'='1 -- ALWAYS TRUE

'+AND+'1'='2 -- ALWAYS FALSE 

```

so lets inject always false into this request in the TrackingID

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%203.png)

So Zero matches of the “Welcome back!” message and no error from the site so the application is checking is the TrackingId is valid or not on whether or not to display the welcome back message, this is basically a Conditional Response.

**What can we do with conditional response?** 

- well we can use this conditional message to extract data based off of whether a condition is true or not.
    - Since we were provided with a table name we can use that to determine whether or not the table does exist.

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%204.png)

now lets get the length of the password since we already know the columns are username and password lets try to get the length of the password of the admin 

to do this we have the LENGTH() Function in SQL 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%205.png)

now that we can see the query works lets change it to = and send it into intruder to brute force the numbers for length of the password

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%206.png)

so the length of the password is 20. 

Now lets try and brute force the password length. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%207.png)

**Brute forcing the password**

- lets use cluster bomb attack to brute for the password.

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%208.png)

**And there we have it we got the password.** 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%20705013c1db184e93b00e00fd862a5bb8/Untitled%209.png)