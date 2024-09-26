# [Oauth] Lab: SSRF via OpenID dynamic client registration (1)

---

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled.png)

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled%201.png)

Lets do some recon on the OAuth Site: 

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled%202.png)

lets go to config page: 

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled%203.png)

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled%204.png)

lets try register our own to get our own ClientID:

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled%205.png)

![Untitled](%5BOauth%5D%20Lab%20SSRF%20via%20OpenID%20dynamic%20client%20registr%20b2a51160efb348de88bd4f0184984e5f/Untitled%206.png)

now lets see if we can have it make request to `http://169.254.169.254/latest/meta-data/iam/security-credentials/admin/`