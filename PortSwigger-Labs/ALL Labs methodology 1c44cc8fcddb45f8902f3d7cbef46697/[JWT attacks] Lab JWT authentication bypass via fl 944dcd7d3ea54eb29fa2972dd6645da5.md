# [JWT attacks]: Lab: JWT authentication bypass via flawed signature verification (1)

---

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20fl%20944dcd7d3ea54eb29fa2972dd6645da5/Untitled.png)

**JWT EDITOR:** 

after logging in: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20fl%20944dcd7d3ea54eb29fa2972dd6645da5/Untitled%201.png)

lets set the `alg: "none"` 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20fl%20944dcd7d3ea54eb29fa2972dd6645da5/Untitled%202.png)

since the server didn't check the signature on the server side to ensure it is valid I was able to set the token to none. 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20fl%20944dcd7d3ea54eb29fa2972dd6645da5/Untitled%203.png)

lets delete carlos 

**Lab Solved:** 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20fl%20944dcd7d3ea54eb29fa2972dd6645da5/Untitled%204.png)