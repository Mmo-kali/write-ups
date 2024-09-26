# [HTTP request smuggling] Lab: HTTP request smuggling, confirming a TE.CL vulnerability via differential responses (1)

---

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled.png)

testing make sure we can post to the root endpoint: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%201.png)

lest test verify front end is using TE: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%202.png)

invalid request rejected by front end. 

now to confirm its [Te.CL](http://Te.CL) lets send another payload : 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%203.png)

and we get time out because the content length of 6 used by back end never gets that last byte so it is waiting for it and times out.

the front end never sends our `X` because the TE used by front end considers the end of the chunk right after that final zero. and the two carriage return and line feed.

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%204.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%205.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%206.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%207.png)

**For the content len and chunk size:** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20HTTP%20request%20smugglin%202158563047ec453bbd41ed0693419a95/Untitled%208.png)

for the chunk size