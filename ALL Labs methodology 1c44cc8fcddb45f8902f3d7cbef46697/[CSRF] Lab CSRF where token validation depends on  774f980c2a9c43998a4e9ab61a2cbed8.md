# [CSRF] Lab: CSRF where token validation depends on token being present (1)

---

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled.png)

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled%201.png)

let's see what happens when we remove the CSRF token. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled%202.png)

so if we remove the token the application isn’t throwing any type of error for the CSRF token being missing. 

lets generate our CSRF PoC . 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled%203.png)

lets test our Payload in the exploit server: 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled%204.png)

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled%205.png)

lets deliver this exploit now. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%20774f980c2a9c43998a4e9ab61a2cbed8/Untitled%206.png)