# [Insecure deserialization] Lab: Modifying serialized data types (1)

---

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled.png)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%201.png)

again like previous lab we can see a base64 cookie: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%202.png)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%203.png)

we need to try to cause the lab to use the PHP loose comparison to set our cookie for the user administrator: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%204.png)

but wait what if we set the data type of the access token to an integer then make the integer `0` since in PHP any string compared to `0`  is true.

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%205.png)

had to fix some stuff and create PHP script to help my understanding: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%206.png)

then encoding the object from my script in base64 and passing that as the cookie: 

[https://www.notion.so](https://www.notion.so)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%207.png)

successfully logged in now lets change cookie in browser:

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%208.png)

and there we got: 

**LAB SOLVED!!!**

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%2061b7a68a24cb4a24823dcfe561de384a/Untitled%209.png)