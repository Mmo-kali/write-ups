# [WebSockets] Lab: Manipulating WebSocket messages to exploit vulnerabilities (1)

---

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled.png)

when opening the site and going to the chat feature we can see the following interesting request and responses from client to server. : 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%201.png)

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%202.png)

the message is being parsed/encoded. 

now lets see how we can use repeater to test different values we can pass to this chat to try exploit a reflected XSS vulnerability. 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%203.png)

one thing that comes to mind is that the `string.replace` method in java script only replaces the first instance depending on how it is implemented 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%204.png)

from : [https://www.w3schools.com/jsref/jsref_replace.asp](https://www.w3schools.com/jsref/jsref_replace.asp)

therefore if I send two of any character on the first character will be encoded. 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%205.png)

but we’re still within a string context so lets use <img tag to cause error. 

payload: 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%206.png)

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20WebSocket%20messages%20t%200c2f6f03e7f3417a8e631655b96c66d4/Untitled%207.png)