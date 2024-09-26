# [HTTP request smuggling] Lab: H2.CL request smuggling (1)

---

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled.png)

**Looking for possible interesting facts:** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%201.png)

**Contents from that js file:** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%202.png)

### Testing for the [H2.CL](http://H2.CL) vulnerability:

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%203.png)

with this provided payload if the application times out that process that the back end is using the provided content length of 12 but is freezing because is doesn't get that 12 byte and is waiting for it since our  search=test is only of size 11: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%204.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%205.png)

now let's exploit this vulnerability. 

**First step: build PoC to alert(document.cookie)** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%206.png)

**Step 2: smuggle our get request to the exploit server by making http/2 send the entire frame of contents but setting the content length of the request to a abritary value so that the back end excuses our smuggled get request and appends it to beginning of next request:** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%207.png)

able to force a invalid request. 

but now we need to find site redirect which we can do with omitting the last slash in a directory: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%208.png)

**But we need to make this redirect off site so lets add a second host header.**

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%209.png)

**When we follow redirect:** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%2010.png)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%2011.png)

**Lab solved:** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Lab%20H2%20CL%20request%20smuggli%200092dbf87e0641138e06c1ca97758087/Untitled%2012.png)