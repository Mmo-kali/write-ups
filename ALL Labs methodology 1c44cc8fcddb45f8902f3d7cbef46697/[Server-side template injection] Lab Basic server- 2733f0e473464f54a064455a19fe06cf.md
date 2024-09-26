# [Server-side template injection] Lab: Basic server-side template injection (code context) (1)

---

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled.png)

Looking at the preferred name functionality: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%201.png)

since it is rendering our user input within a code context lets try to add HTML tag at the end to see how our web app reacts. 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%202.png)

After sending that request this error I got. 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%203.png)

some type python being used.

 **template engine**: tornado template engine

lets play around to see what we can get to work: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%204.png)

result: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%205.png)

test:

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%206.png)

**this was evaluated:** 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%207.png)

show the result of 5*5 = 25

so inorder to run a command I need to import some library in python: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%208.png)

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%209.png)

Resource: [https://ajinabraham.com/blog/server-side-template-injection-in-tornado](https://ajinabraham.com/blog/server-side-template-injection-in-tornado)

now lets change ls to `rm morale.txt` 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Basic%20server-%202733f0e473464f54a064455a19fe06cf/Untitled%2010.png)

**Lab solved**