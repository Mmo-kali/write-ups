# [XSS] Lab: Reflected DOM XSS (1)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled.png)

lets inject a canary and search for it within the inspect page of the web site the canary I will use os ‘lb115’

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%201.png)

let's also look at our network tab in inpect tool for all request being made. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%202.png)

lets look at the contents of this response. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%203.png)

so it is in JSON, and it is echoing our own search term, and I could be wrong but before we look at our code I think we might be able to exploit this if there is no sanitation provided. 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%204.png)

so this searchresults.js takes our search term places it into how search results object that we see in json above, from there it uses a function to display our search term and results. 

it basically parses the JSON object for the name and echo it into the web page with the 

```jsx
 var searchTerm = searchResultsObj.searchTerm
```

so I think if we can somehow escape the JSON string and inject some type of javascript function since we’re within the context of a script because the eval function is going to pass and execute whatever is provided to it. There is no sanitization so right now we’re within a script context.

lest try a payload with json string of “\-alert(1) 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%205.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%206.png)

tool I found for json escaping: 

[Free Online JSON Escape / Unescape Tool - FreeFormatter.com](https://www.freeformatter.com/json-escape.html#before-output)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%207.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%208.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20DOM%20XSS%20(1)%20ae7e3712306f45d7ac8bce350b6689a8/Untitled%209.png)