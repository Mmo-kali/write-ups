# [File Path Traversal] Lab: File path traversal, traversal sequences stripped with superfluous URL-decode (1)

---

This lab is apart of my path way towards my BSCP 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%2035161d918c4c444b981a08255046b676/Untitled.png)

let see where we can possibly do path traversal by visiting the site and understand the structure and layout. 

It is a site with multiple products with images being loaded, by capturing that request of getting the image im able to possibly exploit the application. 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%2035161d918c4c444b981a08255046b676/Untitled%201.png)

to solve this lab we will url encode out payload twice since the defensive mechanism in place only decodes it once to look for path traversal sequences. 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%2035161d918c4c444b981a08255046b676/Untitled%202.png)

Now we solved the lab: 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%2035161d918c4c444b981a08255046b676/Untitled%203.png)