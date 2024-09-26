# [JWT attacks] Lab: JWT authentication bypass via jwk header injection (1)

---

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jw%20b681293f2fe64c9bb20bacefbf04dcfb/Untitled.png)

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jw%20b681293f2fe64c9bb20bacefbf04dcfb/Untitled%201.png)

lets send this to repeater, and look at the jwt with the extension: 

lets generate our own RSA key: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jw%20b681293f2fe64c9bb20bacefbf04dcfb/Untitled%202.png)

what we’re going to do with this is use the extension to embed the jwk into our jwt which will contain our own RSA key since the server is accepting anytype of RSA key that is passed 

so first lets change sub to “carlos” then go to the bottom left hit attack and embed jwk 

then select the RSA 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jw%20b681293f2fe64c9bb20bacefbf04dcfb/Untitled%203.png)

now lets change it to administrator

then request /admin: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jw%20b681293f2fe64c9bb20bacefbf04dcfb/Untitled%204.png)

**Lab Solved:** 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jw%20b681293f2fe64c9bb20bacefbf04dcfb/Untitled%205.png)