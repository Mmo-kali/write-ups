# [File Path Traversal] Lab: File path traversal, traversal sequences stripped non-recursively (1)

---

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%204cfd74b364d14257ba0412ffe1a8179f/Untitled.png)

This lab is apart of my path towards my BSCP cert. 

Lets visit the application see where we can possibly exploit this application. 

When selecting on of the product we can see the image is being refrenced in a insecure manner. 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%204cfd74b364d14257ba0412ffe1a8179f/Untitled%201.png)

now lets test to see what defense mechanisms are in place. 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%204cfd74b364d14257ba0412ffe1a8179f/Untitled%202.png)

after doing my testing i may need to use nested traversal sequence in order to by pass the stripping. 

![Untitled](%5BFile%20Path%20Traversal%5D%20Lab%20File%20path%20traversal,%20tra%204cfd74b364d14257ba0412ffe1a8179f/Untitled%203.png)

and there we have it lab solved. the reason i user ….// is because the web app is only gonna strip ../ therfore leaving us with ../ still in the injected command.