# [XSS] Lab: Reflected XSS into a JavaScript string with angle brackets and double quotes HTML-encoded and single quotes escaped (1)

---

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%2077dc29822ae6486dadff21209d905252/Untitled.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%2077dc29822ae6486dadff21209d905252/Untitled%201.png)

so the website is taking the input that we’re providing from the search query and placing it within the context of a HTML tag as well as a img src tag and within a <script> tag 

so lets try exploit the way this website is escaping our characters 

```jsx
'\'' <-- Search term 

What happens is our first quote is 
```

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%2077dc29822ae6486dadff21209d905252/Untitled%202.png)

by simple adding a \before any quote we can escape it tricking program into porvid toe slashed with them canceling each other out. not to run my own alert(1) I need to close this code with a semi colon ; and then just add alert(1) 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%2077dc29822ae6486dadff21209d905252/Untitled%203.png)

right now there is a error in our java script code because we can see that the document.write isn't executing. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%2077dc29822ae6486dadff21209d905252/Untitled%204.png)

this was the payload: 

```jsx
https://labID.web-security-academy.net/?search=\'; alert(1)//'
```

to by-pass the error I simple just added two forward slashes to comment out the rest of the java script. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%2077dc29822ae6486dadff21209d905252/Untitled%205.png)