# [Prototype Pollution] Lab: DOM XSS via client-side prototype pollution (1)

---

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled.png)

Check the current proto type for the object at runtime: 

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%201.png)

lets try to inject our own key, and identify a possible source: 

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%202.png)

now find gadget: 

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%203.png)

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%204.png)

in the js we can set break point in the console by clicking on the line number. 

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%205.png)

now lets define our own transport_url

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%206.png)

![Untitled](%5BPrototype%20Pollution%5D%20Lab%20DOM%20XSS%20via%20client-side%20%20f8f4f8eef7964724956e295747503a01/Untitled%207.png)