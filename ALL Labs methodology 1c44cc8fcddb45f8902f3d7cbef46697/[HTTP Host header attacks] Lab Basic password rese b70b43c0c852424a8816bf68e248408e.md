# [HTTP Host header attacks] Lab: Basic password reset poisoning (1)

---

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled.png)

since he will click on any links sent to him what if we can possibly changes the email of his account then do a password reset? 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%201.png)

lets try reset our own password: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%202.png)

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%203.png)

now how is the site generating the URL for that token? 

well if its using host header we can possibly exploit it but sending the email to carlos with the URL being a arbitrary website by changing the host header. 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%204.png)

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%205.png)

lets change host to our exploit server 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%206.png)

now clicking on that link give use a request in access log with reset token in query string. 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%207.png)

since that worked lets change username to carlos: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%208.png)

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%209.png)

now lets go to the site again with the directory and change password: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Basic%20password%20rese%20b70b43c0c852424a8816bf68e248408e/Untitled%2010.png)