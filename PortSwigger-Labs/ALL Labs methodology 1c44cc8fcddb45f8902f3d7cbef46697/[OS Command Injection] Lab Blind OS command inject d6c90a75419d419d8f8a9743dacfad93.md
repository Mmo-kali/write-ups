# [OS Command Injection] Lab: Blind OS command injection with output redirection (1)

---

This lab is apart of my journey towards my BSCP. 

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled.png)

Lets visit the site without a proxy.

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%201.png)

I went to the feedback page of the application because sometimes websites will implement this functionality of sending feedback via email with the mail command in linux. with this direct access to the cli of the machine we can possibly escape the command and be able to place a arbitrary command to be able to run or execute anything we would like. lets first find which field we can exploit with the sleep command in linux to cause a time delay. 

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%202.png)

so we can see that it is the email field. since when we inject the sleep command there is a time delay of ten seconds from the response. 

- Now lets create a file in the writable directory /var/www/images

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%203.png)

using a test file then lets do a get request for that file. 

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%204.png)

so we can see it worked not lets create a script that will run the whoami command 

so now we can just simply run the whoami command and redirect that output into a test file then request that file. 

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%205.png)

now lets request that file. 

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%206.png)

now we can see that we got the output of the whoami command redirected to the file called whoami.txt 

![Untitled](%5BOS%20Command%20Injection%5D%20Lab%20Blind%20OS%20command%20inject%20d6c90a75419d419d8f8a9743dacfad93/Untitled%207.png)