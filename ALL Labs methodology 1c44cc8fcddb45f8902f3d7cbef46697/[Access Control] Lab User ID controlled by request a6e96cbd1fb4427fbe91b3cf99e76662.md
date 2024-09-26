# [Access Control] Lab: User ID controlled by request parameter with data leakage in redirect (1)

---

![Untitled](%5BAccess%20Control%5D%20Lab%20User%20ID%20controlled%20by%20request%20a6e96cbd1fb4427fbe91b3cf99e76662/Untitled.png)

lets login to the provided account then change the my-account id=carlos lets see what happens. 

when we change the User ID to carlos we get: 

![Untitled](%5BAccess%20Control%5D%20Lab%20User%20ID%20controlled%20by%20request%20a6e96cbd1fb4427fbe91b3cf99e76662/Untitled%201.png)

---

a 302 but when we render that 302 we can see we still get the API key .

![Untitled](%5BAccess%20Control%5D%20Lab%20User%20ID%20controlled%20by%20request%20a6e96cbd1fb4427fbe91b3cf99e76662/Untitled%202.png)