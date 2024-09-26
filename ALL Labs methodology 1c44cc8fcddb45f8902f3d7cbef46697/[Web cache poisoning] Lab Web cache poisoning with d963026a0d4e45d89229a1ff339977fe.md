# [Web cache poisoning] Lab: Web cache poisoning with an unkeyed cookie (1)

---

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%20d963026a0d4e45d89229a1ff339977fe/Untitled.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%20d963026a0d4e45d89229a1ff339977fe/Untitled%201.png)

and cookie is being set again: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%20d963026a0d4e45d89229a1ff339977fe/Untitled%202.png)

now when putting it into the repeater and getting a cache hit we can see the cookie value being reflected into a `<script>`  TAGS 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%20d963026a0d4e45d89229a1ff339977fe/Untitled%203.png)

we’re within a json string. 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%20d963026a0d4e45d89229a1ff339977fe/Untitled%204.png)

the reason the `-` breaks the syntax is because JSON interprets it as a subtraction operator, which breaks the syntax

---