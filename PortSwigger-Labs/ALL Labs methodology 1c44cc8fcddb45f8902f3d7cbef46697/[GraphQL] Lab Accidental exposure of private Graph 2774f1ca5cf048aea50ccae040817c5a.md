# [GraphQL] Lab: Accidental exposure of private GraphQL fields (1)

---

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled.png)

### GraphQL endpoint:

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled%201.png)

now that we located endpoint and its two scripts lets get the schema.

### Schema:

- to get schema lets send the post request to the repeater and then change to introspection.
- 

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled%202.png)

**Lets visualize this:** 

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled%203.png)

tool: [http://nathanrandal.com/graphql-visualizer/](http://nathanrandal.com/graphql-visualizer/)

so we need to query type of `getUser`

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled%204.png)

when you pass `getUser($id:1)` will give error since the $id is a query string to pass the id in the () we use `getUser(id:1)`

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled%205.png)

![Untitled](%5BGraphQL%5D%20Lab%20Accidental%20exposure%20of%20private%20Graph%202774f1ca5cf048aea50ccae040817c5a/Untitled%206.png)