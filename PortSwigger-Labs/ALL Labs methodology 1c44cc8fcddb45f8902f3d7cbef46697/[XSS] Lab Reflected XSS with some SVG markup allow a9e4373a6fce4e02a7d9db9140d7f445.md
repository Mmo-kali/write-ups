# [XSS] Lab: Reflected XSS with some SVG markup allowed (1)

---

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20with%20some%20SVG%20markup%20allow%20a9e4373a6fce4e02a7d9db9140d7f445/Untitled.png)

so since it allows SVG tags I just tried with the basic <SVG> payload: 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20with%20some%20SVG%20markup%20allow%20a9e4373a6fce4e02a7d9db9140d7f445/Untitled%201.png)

lets use intruder to get all the tags that worked. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20with%20some%20SVG%20markup%20allow%20a9e4373a6fce4e02a7d9db9140d7f445/Untitled%202.png)

we can use the window screen shot tool to extract the tags that passed then pass them again in a pitch fork attack. only thing we will need to use burp suite to remove the ‘<’ and ‘>’ symbols. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20with%20some%20SVG%20markup%20allow%20a9e4373a6fce4e02a7d9db9140d7f445/Untitled%203.png)

so as we lets intruder run lets continue googling trying to see what we can learn about svg. 

so I just had a set of events pass: 

so one of the issue I had with this lab was one of my tag called animatetransform I had that tag with a capital ‘T’

after fix that issue we can see we can call a <SVG> and <animatetransform> inside of the SVG to cause a type of animation event to occur for us to be able to use the onbegin event handler so in the end our payload looked like this: 

```html
<svg> <animatetransform onbegin="alert(1)">
```

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20with%20some%20SVG%20markup%20allow%20a9e4373a6fce4e02a7d9db9140d7f445/Untitled%204.png)