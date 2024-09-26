# [GraphQL] Lab: Bypassing GraphQL brute force protections (1)

---

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled.png)

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%201.png)

lets visualize the schema : 

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%202.png)

now lets try login: 

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%203.png)

Lets craft our payload with aliases which allows us to send multiple queries in one HTTP request  

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%204.png)

since the login field is a mutation we need to include our aliases within the `mutation {  **Aliases go here** }` 

**EXAMPLE:** 

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%205.png)

found password: 

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%206.png)

**THIS IS PASSWORD:** 

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%207.png)

![Untitled](%5BGraphQL%5D%20Lab%20Bypassing%20GraphQL%20brute%20force%20protec%204a2f84729a0b42a09ad4e158d1f45c60/Untitled%208.png)