# [HTTP Host header attacks] Lab: Routing-based SSRF (1)

---

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Routing-based%20SSRF%20%20890fe6e4db6e4170ad8b728f63c36a9e/Untitled.png)

some info from the error: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Routing-based%20SSRF%20%20890fe6e4db6e4170ad8b728f63c36a9e/Untitled%201.png)

lets use intruder to figure out which address it is: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Routing-based%20SSRF%20%20890fe6e4db6e4170ad8b728f63c36a9e/Untitled%202.png)

address is `192.168.0.106`

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Routing-based%20SSRF%20%20890fe6e4db6e4170ad8b728f63c36a9e/Untitled%203.png)

now that we have admin page lets delete the user: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Routing-based%20SSRF%20%20890fe6e4db6e4170ad8b728f63c36a9e/Untitled%204.png)

**Lab solved**

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Routing-based%20SSRF%20%20890fe6e4db6e4170ad8b728f63c36a9e/Untitled%205.png)