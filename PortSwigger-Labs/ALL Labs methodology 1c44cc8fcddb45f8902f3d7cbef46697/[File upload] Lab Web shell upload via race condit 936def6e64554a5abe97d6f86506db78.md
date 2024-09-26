# [File upload] Lab: Web shell upload via race condition (1)

---

**EXPERT LAB** 

This lab is apart of my journey toward my BSCP. 

![Untitled](%5BFile%20upload%5D%20Lab%20Web%20shell%20upload%20via%20race%20condit%20936def6e64554a5abe97d6f86506db78/Untitled.png)

First let's visit the website without a proxy to map out the application and get an understanding of how it is made and designed and the functionality of the application to possibly see any points for file uploads. 

after logging into the winner:peter account the we were provide with we can see there is a file upload for the avatar for my account: 

![Untitled](%5BFile%20upload%5D%20Lab%20Web%20shell%20upload%20via%20race%20condit%20936def6e64554a5abe97d6f86506db78/Untitled%201.png)

lets use foxy proxy and try to upload a PHP file to see what type of response we get back. 

![Untitled](%5BFile%20upload%5D%20Lab%20Web%20shell%20upload%20via%20race%20condit%20936def6e64554a5abe97d6f86506db78/Untitled%202.png)

lets see if there is a possible way to bypass the file validation. 

one of the things we can use is the source code provided in the hint. 

![Untitled](%5BFile%20upload%5D%20Lab%20Web%20shell%20upload%20via%20race%20condit%20936def6e64554a5abe97d6f86506db78/Untitled%203.png)