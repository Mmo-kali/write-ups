# [DOM Vuln] Lab: DOM-based open redirection (1)

---

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20open%20redirection%20(1)%201a14eab072f3434386b3257f4070719a/Untitled.png)

lest see functionality of the website when we are navigating to different pages. 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20open%20redirection%20(1)%201a14eab072f3434386b3257f4070719a/Untitled%201.png)

so one things I did was looked at all button and <href that I can use to be redirected. 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20open%20redirection%20(1)%201a14eab072f3434386b3257f4070719a/Untitled%202.png)

i was able to use a tool I have called web dev which is a extension on chrome and enable all href details 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20open%20redirection%20(1)%201a14eab072f3434386b3257f4070719a/Untitled%203.png)

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20open%20redirection%20(1)%201a14eab072f3434386b3257f4070719a/Untitled%204.png)

this script is looking from and URL after the url= parameter and if it doesn't find one it just takes the current URL. so lets add our own URL 

 

```jsx
https://.web-security-academy.net/post?postId=4&url=https://exploit-0a18002c0391f7a6808d9d7b016a00aa.exploit-server.net/
```

and there we have it lab solved: 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20open%20redirection%20(1)%201a14eab072f3434386b3257f4070719a/Untitled%205.png)