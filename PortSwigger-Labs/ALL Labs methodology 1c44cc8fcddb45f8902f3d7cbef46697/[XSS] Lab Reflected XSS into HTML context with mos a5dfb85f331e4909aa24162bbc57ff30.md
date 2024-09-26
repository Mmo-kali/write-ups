# [XSS] Lab: Reflected XSS into HTML context with most tags and attributes blocked (1)

---

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled.png)

since we have a search box lets insert a canary and look for where it appears in the source/DOM. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled%201.png)

by injecting a comment sequence we can see that we’re able to inject a comment sequence. 

since this lab is blocking most tags lets use intruder to see which ones we can use. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled%202.png)

the only one that passed was body: 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled%203.png)

now lets see which events it is blocking:  

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled%204.png)

so there was a couple of different tags. 

but the 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled%205.png)

but the important one is the onresize tag. 

we can pass this through an iframe allowing us to create a onload event to have our iframe resized. 

the original source of the iframe with be our URL with the search query in the URL. 

 

<iframe id="test" src="[https://0a39003a04afa69f8288a7b20027008c.web-security-academy.net/?search=<body+onresize%3D"print()">](https://0a39003a04afa69f8288a7b20027008c.web-security-academy.net/?search=%3Cbody+onresize%3D%22print%28%29%22%3E)" onload=this.style.width='100px'> </iframe>

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20HTML%20context%20with%20mos%20a5dfb85f331e4909aa24162bbc57ff30/Untitled%206.png)