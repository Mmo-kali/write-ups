# [HTTP Host header attacks] Lab: SSRF via flawed request parsing (1)

---

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20SSRF%20via%20flawed%20req%2018271268566648518ca1be3a4d3df950/Untitled.png)

so lets do some testing to see exactly which parsing flaw does this application have: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20SSRF%20via%20flawed%20req%2018271268566648518ca1be3a4d3df950/Untitled%201.png)

seems to me the application is looking just for the full path of the website within host header other wise we get 403 so my thinking was lets request the full path of this domain and it worked. 

now lets use intruder: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20SSRF%20via%20flawed%20req%2018271268566648518ca1be3a4d3df950/Untitled%202.png)

result: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20SSRF%20via%20flawed%20req%2018271268566648518ca1be3a4d3df950/Untitled%203.png)

lets request that in the browser and delete Carlos 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20SSRF%20via%20flawed%20req%2018271268566648518ca1be3a4d3df950/Untitled%204.png)

**Lab solved:** 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20SSRF%20via%20flawed%20req%2018271268566648518ca1be3a4d3df950/Untitled%205.png)