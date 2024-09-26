# [CSRF] Lab: CSRF where token is not tied to user session (1)

---

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled.png)

so after capturing the request for the change email and trying to use a hold csrf token we can see that is doesn't work since the token was already used and is therefore invalid. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled%201.png)

**TESTING**

so I'm going to intercept the request with burp proxy and capture the csrf token that wiener:peter has then I'm going to try nd use that CSRF token with carlos:Montoya account to see if it treats it as a valid csrf token.  

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled%202.png)

CSRF from wiener:peter 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled%203.png)

captured the request from carlos now lets forward to repeater 

can set the csrf token to wieners csrf token. 

also I'm gonna save carlos csrf token because if this works ill reuse his token to deliver the exploit to the victim. 

`csrf=GCUDtRAblWvks3ElfOmwT9v5z3IrnGSE` ← WIENER  

`csrf=gvfcxd8Aq8O3NlxAf78pz7Wuvr7XB9uv <-- CARLOS`

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled%204.png)

so it worked so what we know now is that the CSRF token is not tied to the session token therefore we can inject a unused but still valid csrf token like the one I saved from carlos to deliver this exploit to the victim. 

lets generate the CSRF PoC 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled%205.png)

let's put that into our exploit server and deliver it to our victim. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20not%20tied%20to%20user%20se%206e15e357df0e47c7a42825a7a506f886/Untitled%206.png)