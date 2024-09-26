# [XSS] Lab: Reflected XSS into a JavaScript string with a single quote and backslash escaped (1)

---

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%20494b917b6e2642678fb6301f23bc850d/Untitled.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%20494b917b6e2642678fb6301f23bc850d/Untitled%201.png)

[encodeURIComponent() - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent)

so turns out that the  **`encodeURIComponent()`** function encodes a [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) by replacing each instance of certain characters by one, two, three, or four escape sequences representing the [UTF-8](https://developer.mozilla.org/en-US/docs/Glossary/UTF-8) encoding of the character

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%20494b917b6e2642678fb6301f23bc850d/Untitled%202.png)

so we can use a single quote to try and escape this function. 

**What if we provide a </script> tag?** 

since it does var searchterm = ‘userInput’ we can exploit that line of code before we get the the encoding step of the code by simple add a </script> tag 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%20494b917b6e2642678fb6301f23bc850d/Untitled%203.png)

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%20494b917b6e2642678fb6301f23bc850d/Untitled%204.png)

now since we’re able to escape that java script tag we can inject our own tags as such: 

![Untitled](%5BXSS%5D%20Lab%20Reflected%20XSS%20into%20a%20JavaScript%20string%20w%20494b917b6e2642678fb6301f23bc850d/Untitled%205.png)