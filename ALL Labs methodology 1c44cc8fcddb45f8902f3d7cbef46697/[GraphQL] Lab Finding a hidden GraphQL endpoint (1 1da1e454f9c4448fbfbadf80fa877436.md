# [GraphQL] Lab: Finding a hidden GraphQL endpoint (1)

---

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled.png)

by doing scan I found: 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%201.png)

from the academy : 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%202.png)

Result: 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%203.png)

now let change it to introspection:

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%204.png)

not allowed let try include `\n`  after __schema since that is what is being blocked 

**RESULTS:** 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%205.png)

now we have schema lets craft our query by first visualizing this 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%206.png)

**EXPLOIT:** 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%207.png)

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%208.png)

but look at this is schema: 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%209.png)

now that we have mutation from the schema we can delete user carlos with id of 3

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%2010.png)

**REQUEST:** 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%2011.png)

**LAB SOLVED:** 

![Untitled](%5BGraphQL%5D%20Lab%20Finding%20a%20hidden%20GraphQL%20endpoint%20(1%201da1e454f9c4448fbfbadf80fa877436/Untitled%2012.png)