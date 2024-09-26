# [JWT attacks]: Lab: JWT authentication bypass via unverified signature (1)

---

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20un%205ce7f744da49408e90f50009daaa45eb/Untitled.png)

**Using the JWT extension we get traffic in the proxy highlighted that contains a JWT.** 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20un%205ce7f744da49408e90f50009daaa45eb/Untitled%201.png)

send that request to repeater: 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20un%205ce7f744da49408e90f50009daaa45eb/Untitled%202.png)

maybe the lab doesn't correctly check for the signature. 

so lets change the username to administrator and go to `/my-account`

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20un%205ce7f744da49408e90f50009daaa45eb/Untitled%203.png)

we get 200 so not lets request `/admin` 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20un%205ce7f744da49408e90f50009daaa45eb/Untitled%204.png)

lets modify the cookie in our browser to make this easier then delete carlos : 

![Untitled](%5BJWT%20attacks%5D%20Lab%20JWT%20authentication%20bypass%20via%20un%205ce7f744da49408e90f50009daaa45eb/Untitled%205.png)