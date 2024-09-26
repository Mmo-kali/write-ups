# [GraphQL] Lab: Accessing private GraphQL posts (1)

---

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled.png)

### GraphQL endpoint

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%201.png)

JS script: 

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%202.png)

JS script for blog summaries: 

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%203.png)

### GraphQL Schema

- Now we need to find the Schema, we can use introspection to query the API for information about the schema.

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%204.png)

right-click in repeater 

now that I set it to introspection query we can get the entire schema from the API: 

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%205.png)

now using a web tool to visualize the schema we can see the schema by pasting our response into the tool: 

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%206.png)

tool: [http://nathanrandal.com/graphql-visualizer/](http://nathanrandal.com/graphql-visualizer/)

one of the things that I'm wondering is if I can send a request and get all the blog posts when the isPrivate is set to true. 

but also notice: 

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%207.png)

here I add isPrivate to the request. 

now notice when we click on a different post it changes from blog summaries to getBlog post: 

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%208.png)

now if we add postPassword: 

we solve the lab

![Untitled](%5BGraphQL%5D%20Lab%20Accessing%20private%20GraphQL%20posts%20(1)%20a7b6f671920f435284a03c92e260eb9c/Untitled%209.png)