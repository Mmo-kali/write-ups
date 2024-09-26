# [HTTP request smuggling] Lab: HTTP/2 request smuggling via CRLF injection (1)

---

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled.png)

get this error: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled%201.png)

lets add headers with value of transfer encoding.

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled%202.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled%203.png)

I'm going to use the comment section to get request of our victim : 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled%204.png)

lets play with content length get cookie I started at 999 and got it: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled%205.png)

lets change cookies with our cookie editor and boom! 

lab solved: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%202%20request%20smuggl%201a693aec457b495ca0f2445ce9ccf933/Untitled%206.png)