# [JWT attacks] Lab: JWT authentication bypass via jku header injection (1)

---

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled.png)

After login 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%201.png)

lets generate a RSA Key and add it to a array of keys into our exploit server: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%202.png)

Add to exploit server: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%203.png)

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%204.png)

now since the server is fetching keys from external domains we can just inject a jku and set its value to the URL of our exploit server. 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%205.png)

not lets sign this with our generate RSA key. 

and send the request: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%206.png)

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20jk%2070dfa398bbdb42b88bfa4ffe1add52a2/Untitled%207.png)