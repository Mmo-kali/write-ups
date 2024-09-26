# [HTTP request smuggling] Lab: HTTP request smuggling, obfuscating the TE header (1)

---

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled.png)

Checking for a post: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%201.png)

let's send our default payload to confirm this is a TE.TE vulnerability, then we will figure out the obfuscated header we need to use. 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%202.png)

this was rejected lets modify the request a bit to confirm once more it is TE.TE

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%203.png)

and we got response so it is TE.TE vulnerability 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%204.png)

---

**Find alternate obfuscated TE header**

- Reason for this is that we need one header to be processed by front end then another header processed by back end.

There are potentially endless ways to obfuscate the `Transfer-Encoding` header. For example:

```
c

Transfer-Encoding : chunked

Transfer-Encoding: chunked
Transfer-Encoding: x

Transfer-Encoding:[tab]chunked

[space]Transfer-Encoding: chunked

X: X[\n]Transfer-Encoding: chunked

Transfer-Encoding
: chunked
```

just need the second header: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%205.png)

we got different response here with a time out so something is happening: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%206.png)

my Request: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%2011e9ae79c02843b8bab2c7ff9f3ab43b/Untitled%207.png)