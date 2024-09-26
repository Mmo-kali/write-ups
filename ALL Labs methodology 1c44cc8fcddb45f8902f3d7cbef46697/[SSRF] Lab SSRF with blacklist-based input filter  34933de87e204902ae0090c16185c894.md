# [SSRF] Lab: SSRF with blacklist-based input filter (1)

---

This lab is apart of my journey towards my BSCP 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled.png)

lets visit the site without a proxy on and map out the functionality of this application before we start intercepting any traffic 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%201.png)

looks like a shopping web app and it has a check stock option so if we check the stock of this item we might be able to see the request made to a API in back end to fetch the stock of a particular item. 

This is important to us because this can be exploited for us to be able to have that API call be changed to an internal system call. 

The only issue now is since there is a blacklist implemented we will need to use many obfuscation techniques to see how we can by pass this black list. 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%202.png)

we can see this didn't work…

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%203.png)

I tried getting a URL to redirect, switching from https to HTTP will bypass SSRF filters:

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%204.png)

this gave me a 500.

lets see what type loop back I can access. 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%205.png)

okay so I can’t use [localhost](http://localhost) the blacklist is checking for that. What about 127.0.0.1? 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%206.png)

nope cant do 127.0.0.1; What about 127.1 ? 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%207.png)

ok so 127.1 worked I know /admin is already filtered what about /Admin with capital A 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%208.png)

very good 

now trying to delete carlos we get this error well this is a easy fix 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%209.png)

take that URL paste it into our API query and boom we are done ! 

![Untitled](%5BSSRF%5D%20Lab%20SSRF%20with%20blacklist-based%20input%20filter%20%2034933de87e204902ae0090c16185c894/Untitled%2010.png)