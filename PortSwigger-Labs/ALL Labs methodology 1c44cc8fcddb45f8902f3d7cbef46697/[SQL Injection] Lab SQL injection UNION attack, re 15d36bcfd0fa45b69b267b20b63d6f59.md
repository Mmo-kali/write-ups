# [SQL Injection] Lab: SQL injection UNION attack, retrieving multiple values in a single column (1)

---

This lab is apart of my journey towards my BSCP 

![Untitled](%5BSQL%20Injection%5D%20Lab%20SQL%20injection%20UNION%20attack,%20re%2015d36bcfd0fa45b69b267b20b63d6f59/Untitled.png)

so first lets visit the site without a proxy to map the application out, to do this i don’t use a proxy to intercept request since i just was to get the general layout of the site. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20SQL%20injection%20UNION%20attack,%20re%2015d36bcfd0fa45b69b267b20b63d6f59/Untitled%201.png)

it is a shopping web app with some category filters at the top there lets look at the request that the browser is sending to the web server when i click on one of those filters. so lets turn our proxy on now to intercept with burp suite and foxy proxy 

![Untitled](%5BSQL%20Injection%5D%20Lab%20SQL%20injection%20UNION%20attack,%20re%2015d36bcfd0fa45b69b267b20b63d6f59/Untitled%202.png)

lets send this to our repeater and figure out how many columns the original query has