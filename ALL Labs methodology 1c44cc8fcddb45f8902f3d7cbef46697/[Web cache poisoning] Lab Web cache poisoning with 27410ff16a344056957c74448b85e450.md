# [Web cache poisoning] Lab: Web cache poisoning with an unkeyed header (1)

---

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%201.png)

found this JS: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%202.png)

this is what the script contains:  

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%203.png)

found this reflected vulnerability 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%204.png)

looks like some encoding is present. 

lets test with the 

`X-Forwarded-Host: test.com`

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%205.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%206.png)

got alert: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/4ca89b2c-bfaf-4abf-8c6f-7e919de9218e.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%207.png)

response was cached: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%208.png)

But how do I know the user is going to visit the product page for that specific product? 

**What if I can store the vulnerability on the index page?** 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%209.png)

I also removed the cookie to ensure the response is cached regardless of the session cookie. 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%2010.png)

and there we go lab lab-solved:  

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%2011.png)

---

**other way to solve this:** 

Lets try this since we see that the tracker is writing the content from this directory: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%203.png)

changed path in exploit server to : 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20with%2027410ff16a344056957c74448b85e450/Untitled%2012.png)