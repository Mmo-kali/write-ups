# [XSS] Lab: Reflected XSS into a JavaScript string with angle brackets HTML encoded (1)

---

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%204ef4dcfc0dfa45aa8c9e72efe6dfe25f/Untitled.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%204ef4dcfc0dfa45aa8c9e72efe6dfe25f/Untitled%201.png)

so again we’re being enclosed within single quotes 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%204ef4dcfc0dfa45aa8c9e72efe6dfe25f/Untitled%202.png)

so I did a view input until I got to know that it didn't encode ‘ ; - or ( ) characters so we can effectively escape this javascript string by commenting out the ending of it. 

so the payload was

```jsx
'-alert(1);//
```

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%204ef4dcfc0dfa45aa8c9e72efe6dfe25f/Untitled%203.png)