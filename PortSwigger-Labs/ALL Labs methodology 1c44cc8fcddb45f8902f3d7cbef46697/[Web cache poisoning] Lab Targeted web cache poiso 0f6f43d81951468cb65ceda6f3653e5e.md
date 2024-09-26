# [Web cache poisoning] Lab: Targeted web cache poisoning using an unknown header (1)

---

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%201.png)

lets start with param miner

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%202.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%203.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%204.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%205.png)

there is a script being used to load comments. 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%206.png)

lets add a x-host header

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%207.png)

now lets try use exploit server to have webpage load our own content 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%208.png)

now that we have that working with getting alert to fire. 

but we know that the useragent is apart of the cache key since it was specified in the vary header: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%209.png)

so we need the victims user agent in order to have this attack delivered. 

so what we need to do is some how force user to make some type of request to our exploit server inorder for us to exfiltrate then user agent. 

since the comment section allows HTML lets embed our exploit server into a img src since the img tag will cause a get request to be made on who views the comments. 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%2010.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%2011.png)

now that we have user agent we can add that into the repeater. 

`"user-agent: Mozilla/5.0 (Victim) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.0.0 Safari/537.36"`

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%2012.png)

notice I change the user agent. 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Targeted%20web%20cache%20poiso%200f6f43d81951468cb65ceda6f3653e5e/Untitled%2013.png)