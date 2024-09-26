# [Oauth] Lab: Authentication bypass via OAuth implicit flow (1)

---

![Untitled](%5BOauth%5D%20Lab%20Authentication%20bypass%20via%20OAuth%20implic%203b6dc2aafa36435990aa7eb6525422bf/Untitled.png)

![Untitled](%5BOauth%5D%20Lab%20Authentication%20bypass%20via%20OAuth%20implic%203b6dc2aafa36435990aa7eb6525422bf/Untitled%201.png)

Lets login now 

after the user confirms the consent the redirect_uri is used to go to the `/callback` 

![Untitled](%5BOauth%5D%20Lab%20Authentication%20bypass%20via%20OAuth%20implic%203b6dc2aafa36435990aa7eb6525422bf/Untitled%202.png)

then finally with our access token we query the API, by posting json data with email user name and access token. 

![Untitled](%5BOauth%5D%20Lab%20Authentication%20bypass%20via%20OAuth%20implic%203b6dc2aafa36435990aa7eb6525422bf/Untitled%203.png)

lets see if we can modify this at all maybe changing the email address.

since the access token we have is valid when we query the API if it doesn't ensure our token corresponds do our OAuth user that we can query for anyone info: 

![Untitled](%5BOauth%5D%20Lab%20Authentication%20bypass%20via%20OAuth%20implic%203b6dc2aafa36435990aa7eb6525422bf/Untitled%204.png)

add that session cookie to browser with an extension. 

![Untitled](%5BOauth%5D%20Lab%20Authentication%20bypass%20via%20OAuth%20implic%203b6dc2aafa36435990aa7eb6525422bf/Untitled%205.png)