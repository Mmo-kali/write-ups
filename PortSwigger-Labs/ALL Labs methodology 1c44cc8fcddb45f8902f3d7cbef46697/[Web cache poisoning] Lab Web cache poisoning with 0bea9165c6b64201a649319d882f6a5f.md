# [Web cache poisoning] Lab: Web cache poisoning with multiple headers (1)

---

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled.png)

lets find hidden headers with param miner: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%201.png)

The X-Forwarded-Scheme header is used to specify the scheme (HTTP or HTTPS) used by the client to make the request.

testing the header: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%202.png)

this JS again: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%203.png)

since we know the 2 headers that are being supported 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%204.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%205.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%206.png)

notice the hit: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%207.png)

then request the index page: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%200bea9165c6b64201a649319d882f6a5f/Untitled%208.png)