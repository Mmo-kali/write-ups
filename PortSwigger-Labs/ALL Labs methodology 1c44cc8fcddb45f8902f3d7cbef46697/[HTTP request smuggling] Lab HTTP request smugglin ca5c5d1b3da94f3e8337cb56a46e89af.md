# [HTTP request smuggling] Lab: HTTP request smuggling, basic TE.CL vulnerability (1)

---

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%201.png)

lets add the Transfer encoding and content length but first lets uncheck update content length in burp repeater: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%202.png)

send this post: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%203.png)

see the mistake I made: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%204.png)

this is because the order in which the content is processed by which front or back end is reversed now. 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%205.png)

this is adding a 0 after my G: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%206.png)

this is why: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%207.png)

---

Try again: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%208.png)

now to confirm a TE.CL vulnerability: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%209.png)

Now lets send normal request: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%2010.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%2011.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%20ca5c5d1b3da94f3e8337cb56a46e89af/Untitled%2012.png)