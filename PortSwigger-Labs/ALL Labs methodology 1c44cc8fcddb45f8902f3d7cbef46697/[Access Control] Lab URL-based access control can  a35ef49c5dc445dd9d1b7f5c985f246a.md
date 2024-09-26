# [Access Control] Lab: URL-based access control can be circumvented (1)

---

This lab is apart of my journey towards my BSCP cert 

![Untitled](%5BAccess%20Control%5D%20Lab%20URL-based%20access%20control%20can%20%20a35ef49c5dc445dd9d1b7f5c985f246a/Untitled.png)

so lets visiting the application to see where the access control vulnerability is. 

![Untitled](%5BAccess%20Control%5D%20Lab%20URL-based%20access%20control%20can%20%20a35ef49c5dc445dd9d1b7f5c985f246a/Untitled%201.png)

as we can see we have the admin panel button in top right lets try to access it and see what parameters/headers it is taking in the request .

based off of the information we’re given the website supports a non standard HTTP header:  **X-Original-URL**

lets see how we can use this header to by pass the access control that the application have implemented. 

if we do a get request to index or / then add the x-original-URL header we can possibly gain access to the admin panel 

![Untitled](%5BAccess%20Control%5D%20Lab%20URL-based%20access%20control%20can%20%20a35ef49c5dc445dd9d1b7f5c985f246a/Untitled%202.png)

now lets delete carlos and included the x-original-URL header again. 

even though I got access denied I still solved the lab : 

![Untitled](%5BAccess%20Control%5D%20Lab%20URL-based%20access%20control%20can%20%20a35ef49c5dc445dd9d1b7f5c985f246a/Untitled%203.png)

![Untitled](%5BAccess%20Control%5D%20Lab%20URL-based%20access%20control%20can%20%20a35ef49c5dc445dd9d1b7f5c985f246a/Untitled%204.png)