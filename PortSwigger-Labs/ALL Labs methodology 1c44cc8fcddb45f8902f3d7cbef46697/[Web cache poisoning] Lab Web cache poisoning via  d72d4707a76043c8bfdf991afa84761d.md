# [Web cache poisoning] Lab: Web cache poisoning via an unkeyed query parameter (1)

---

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled%201.png)

notice the hit: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled%202.png)

now a miss so clearly the cache query param is include in the cache key but the utm parameter might be ignored lets see: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled%203.png)

this UTM parameter is unkeyed: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled%204.png)

notice script is included in the request: 

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled%205.png)

![Untitled](%5BWeb%20cache%20poisoning%5D%20Lab%20Web%20cache%20poisoning%20via%20%20d72d4707a76043c8bfdf991afa84761d/Untitled%206.png)