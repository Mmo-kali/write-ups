# [CSRF] Lab: CSRF where token validation depends on request method (1)

---

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled.png)

Lets start by logging in to the Wiener Peter account to view the request and the action we can preform. 

so something to make note of is sometimes when doing a csrf token validation the web application will only be expecting a CSRF token when a certain request method is used so for example if a post request is made it will require the csrf token but not if we make a get request. 

since we need to get a CSRF attack to change the users email lets capture that request: 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled%201.png)

let's send this to the repeater and see if we can use our email parameter in the actual request path and append it with a `?`  to pass it as query string or `&` to specify URL parameter. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled%202.png)

so we can see it is working. let's generate a CSRF PoC. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled%203.png)

let test if it works by view the exploit and changing the email address to a different one then the one we have set right now.

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled%204.png)

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled%205.png)

let deliver this payload. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20validation%20depends%20on%20%206886f0200eed4531b56881c0616d6ca2/Untitled%206.png)