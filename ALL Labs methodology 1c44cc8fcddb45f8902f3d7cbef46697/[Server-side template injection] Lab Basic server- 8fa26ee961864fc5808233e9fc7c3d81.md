# [Server-side template injection] Lab: Basic server-side template injection (1)

---

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled.png)

message in the URL query string is being reflected onto the website: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%201.png)

I'm going to send this to intruder and fuzz it with the built in fuzz list from intruder. 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%202.png)

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%203.png)

got 2 500 errors lets test see if its server interpreting `<%`

not being reflected

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%204.png)

the template syntax is used by ruby: 

`<%= 7 * 7 %>`  passing this in the message string we can see it is being handled by passing the result to the template: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%205.png)

now lets try craft a payload to be able to exploit this system

since our code is being executed by the OS we can just simply issue commands using `<%= `command`` `%>` 

so issuing `<%= ls %>` results: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%206.png)

to solve lab `<%= `rm morale.txt` %>`

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%208fa26ee961864fc5808233e9fc7c3d81/Untitled%207.png)