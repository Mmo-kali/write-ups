# [XSS] DOM XSS in document.write sink using source location.search inside a select element (1)

---

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled.png)

lets go to the site and begin testing for XSS 

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled%201.png)

so for a possible injection point we’re within the context of JS script 

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled%202.png)

since we’re within the context of a HTML tag lets look for a event handler that work with on select 

this is the systax and payload I crafted 

```jsx
<select name="storeId" onselect="alert(1)">
```

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled%203.png)

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled%204.png)

so this worked: 

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled%205.png)

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20document%20write%20sink%20using%20source%20%2090131e0752054f3e9e6062c9889ddd97/Untitled%206.png)

my previous payload didn’t work because syntax error.