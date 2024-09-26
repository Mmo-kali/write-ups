# [Web cache poisoning] Lab: Parameter cloaking (1)

---

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled.png)

when access the index page 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled%201.png)

there is also this JS : 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled%202.png)

notice that the `;`  can be use as a delimiter: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled%203.png)

what if we define two callbacks?

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled%204.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled%205.png)

now we just need to request it till the Age is greater then the cache control max age. 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Parameter%20cloaking%20(1)%2039981840c57847a0be571ab68c536ed0/Untitled%206.png)