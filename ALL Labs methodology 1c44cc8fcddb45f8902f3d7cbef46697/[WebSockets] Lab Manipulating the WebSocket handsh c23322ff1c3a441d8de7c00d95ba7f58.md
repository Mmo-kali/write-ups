# [WebSockets] Lab: Manipulating the WebSocket handshake to exploit vulnerabilities (1)

---

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled.png)

interesting request and response: 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%201.png)

Function for sending messages: 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%202.png)

so there also another interesting thing going on in this script, from my understanding there is not way to bypass this filter besides exploiting the way the filter knows when to be called and that is when the encode value is: `encode=True`  

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%203.png)

but since our messages are being sent over in JSON format what is stopping me from trying to overwrite that value, by manipulating the websocket message. 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%204.png)

to client (NOTICE NO ENCODING):

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%205.png)

then we can see that the <u> tag was evaluated. 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%206.png)

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%207.png)

but my assumption is after the application receives a message when the encoding is false it blacklists the IP: 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%208.png)

so lets request `/chat` but add a header `x-forwarded-for:` to change our IP this means the WebSocket connection should go through again with a new handshake. 

and it worked: 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%209.png)

then when we add the header: 

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%2010.png)

now lets turn intercept on request this then allow for the connection with websockets go through with a new handshake. 

payload I used: 

```jsx
<img src=1 oNeRrOr=alert`1`>
```

![Untitled](%5BWebSockets%5D%20Lab%20Manipulating%20the%20WebSocket%20handsh%20c23322ff1c3a441d8de7c00d95ba7f58/Untitled%2011.png)