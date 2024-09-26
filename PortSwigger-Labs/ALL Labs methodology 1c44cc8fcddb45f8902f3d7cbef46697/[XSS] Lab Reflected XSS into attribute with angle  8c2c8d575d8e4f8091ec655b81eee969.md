# [XSS] Lab: Reflected XSS into attribute with angle brackets HTML-encoded (1)

---

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled.png)

so lets begin by finding the context. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%201.png)

**Note:** Whatever we search for is being added to a h1 tag in HTML surrounded by single quotes. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%202.png)

not that we know that context let's try to escape the value from the input tag first by giving a random value before the double quotes we will use to flee because is we supply just a double quote we will escape our value without not first being assigned making it difficult for us to look for our reflected result also nothing else will be reflected. 

**NOTE THE PAYLOAD WILL WORK IF NOTHING IS PROVIDED BEFORE THE ESCAPE SEQUENCE< BUT FOR TESTING WE SHOULD INCLUDE A CANARY BEFORE OUR ESCAPSE.** 

 since it is an input tag we will need to use a universal event attribute like onfocus and autofocus to call our alert 

 

so first lets see if double quotes escape and what the application does with the character at the end: 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%203.png)

so now we can see we can escape it and inject our own malicious code lets use the onfocus event handler.

this is my payload: 

 note: the double quote at the beginning of alert will be closed by the single quote from the original value attribute. 

```html
lb155" autofocus onfocus="alert(1)
```

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%204.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%205.png)

lab solved: 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%206.png)

---

**COMMUNITY SOLUTION:**

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20attribute%20with%20angle%20%208c2c8d575d8e4f8091ec655b81eee969/Untitled%207.png)

this payload required user interaction my payload did not.