# [CSRF] Lab: CSRF where token is duplicated in cookie (1)

---

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20duplicated%20in%20cooki%20d1931873714c4ef0bb17f8ccdec2572f/Untitled.png)

this was the request made: 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20duplicated%20in%20cooki%20d1931873714c4ef0bb17f8ccdec2572f/Untitled%201.png)

notice the CSRF token is a the same as the session cookie. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20duplicated%20in%20cooki%20d1931873714c4ef0bb17f8ccdec2572f/Untitled%202.png)

```jsx
%0d%0aSet-Cookie:%20csrf=fake%3b%20SameSite=None
```

is we reuse the same payload from the previous lab we can set our own cookie. 

the reason this works is because what ever we set the csrf cookie to is duplicated in the csrf token so as long as the csrf cookie and token are the same we’re fine. 

so lets use same payload with the <img> tag 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20duplicated%20in%20cooki%20d1931873714c4ef0bb17f8ccdec2572f/Untitled%203.png)

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20where%20token%20is%20duplicated%20in%20cooki%20d1931873714c4ef0bb17f8ccdec2572f/Untitled%204.png)