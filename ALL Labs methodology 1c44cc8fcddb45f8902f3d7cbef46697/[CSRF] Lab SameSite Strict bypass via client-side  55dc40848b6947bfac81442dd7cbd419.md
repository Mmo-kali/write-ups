# [CSRF] Lab: SameSite Strict bypass via client-side redirect (1)

---

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled.png)

SameSite restriction is set to strict. 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%201.png)

after leaving a comment we can see a script is loaded: 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%202.png)

this is the .js: 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%203.png)

so this is creating a redirect based off of the blog path that it is getting from the value of the user parameter `postID`  so if some how we can se

the js accepts blank parameters: 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%204.png)

lets see if we can make it redirect to the get 

one thing I noticed is the directory sequence: 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%205.png)

and since we know that we can use a get request for the change email andthat the page automatically redirects after 3000 ms. now we can craft our payload: 

this is the URL: 

```jsx
https://0a6b00be036ae1f181d4cb4d00fc00df.web-security-academy.net/post/comment/confirmation?postId=../../..//my-account/change-email?email=t%40testing.com%26submit=1
```

payload: 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%206.png)

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Strict%20bypass%20via%20client-side%20%2055dc40848b6947bfac81442dd7cbd419/Untitled%207.png)