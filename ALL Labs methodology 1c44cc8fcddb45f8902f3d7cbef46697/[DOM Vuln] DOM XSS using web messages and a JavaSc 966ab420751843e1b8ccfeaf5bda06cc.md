# [DOM Vuln] DOM XSS using web messages and a JavaScript URL (1)

---

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20a%20JavaSc%20966ab420751843e1b8ccfeaf5bda06cc/Untitled.png)

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20a%20JavaSc%20966ab420751843e1b8ccfeaf5bda06cc/Untitled%201.png)

so we have some java script here for a web app that is taking 

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20a%20JavaSc%20966ab420751843e1b8ccfeaf5bda06cc/Untitled%202.png)

what if we use a postMessage with a windowPrint method 

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20a%20JavaSc%20966ab420751843e1b8ccfeaf5bda06cc/Untitled%203.png)

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20a%20JavaSc%20966ab420751843e1b8ccfeaf5bda06cc/Untitled%204.png)

 <iframe src = site id=IframeID> <>

[https://www.notion.so](https://www.notion.so)

var onload = function {

getElementID(iframeID).postMessage(””, iframe.orgin)

};