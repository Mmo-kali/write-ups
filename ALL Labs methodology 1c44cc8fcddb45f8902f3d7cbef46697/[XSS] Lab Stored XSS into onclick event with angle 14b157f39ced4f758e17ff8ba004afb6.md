# [XSS] Lab: Stored XSS into onclick event with angle brackets and double quotes HTML-encoded and single quotes and backslash escaped (1)

---

![Untitled](%5BXSS%5D%20Lab%20Stored%20XSS%20into%20onclick%20event%20with%20angle%2014b157f39ced4f758e17ff8ba004afb6/Untitled.png)

so the website is some type of blog so the common place for XSS here is gonna be in the comment section since those comments are stored. 

![Untitled](%5BXSS%5D%20Lab%20Stored%20XSS%20into%20onclick%20event%20with%20angle%2014b157f39ced4f758e17ff8ba004afb6/Untitled%201.png)

![Untitled](%5BXSS%5D%20Lab%20Stored%20XSS%20into%20onclick%20event%20with%20angle%2014b157f39ced4f758e17ff8ba004afb6/Untitled%202.png)

so the website requires a http or https

![Untitled](%5BXSS%5D%20Lab%20Stored%20XSS%20into%20onclick%20event%20with%20angle%2014b157f39ced4f758e17ff8ba004afb6/Untitled%203.png)

this was the payload: 

```jsx
&apos;-alert(document.domain)-&apos;
```

![Untitled](%5BXSS%5D%20Lab%20Stored%20XSS%20into%20onclick%20event%20with%20angle%2014b157f39ced4f758e17ff8ba004afb6/Untitled%204.png)