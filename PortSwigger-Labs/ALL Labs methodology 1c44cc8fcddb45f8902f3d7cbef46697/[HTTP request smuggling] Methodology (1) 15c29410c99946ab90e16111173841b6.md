# [HTTP request smuggling] Methodology (1)

---

---

**YT playlist:** 

[HTTP Request Smuggling](https://youtube.com/playlist?list=PLGb2cDlBWRUX1_7RAIjRkZDYgAB3VbUSw&si=EGwl5NcgW_AC2EY_)

---

https://book.hacktricks.xyz/pentesting-web/http-request-smuggling

# General 4-step methodology

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled.png)

## Prepare burp for request smuggling:

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%201.png)

---

## How to detect [TE.CL](http://TE.CL) Vulnerabilities with timing techniques (also used for CL.TE)

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/ac85d8b2-26c6-45c9-9234-df7a997c7490.png)

Checking: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%202.png)

why did it reject: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%203.png)

now since this was rejected we have 2 possibilities: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%204.png)

so lets send our other payload: 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%205.png)

**The server timed out now we have successfully identified that the backend has timed out and it is using TE.CL**

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%206.png)

**why do we know it is back end using CL ?** 

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%207.png)

since we know front end is using TL it forwarded the 5 bytes of our chunked message but since back-end is only getting 5 bytes when 6 are being expected this causes a a timeout since the back end is still waiting for its 6th byte 

**EACH CHARACTER IS A BYTE (INCLUDING THE `\n` and `\r`) !**

---

 http smuggling, obfuscating the TE header typically when server use Nginx

## (TE.TE) http smuggling, obfuscating the TE header

- By obfuscating the TE header we're trying to provide a second TE header that is invalid so it can be treated differently on the front end than back-end and that away we force one of servers to process the content length instead

**Turn TE.TE into TE.CL**

- The front end will ignore the malformed TE header, and send request using the chunked encoding whereas the back-end will reject the TE header and process the request using the content-lengh, therfore turning the TE.TE vulnerability into a [TE.CL](http://TE.CL) vulnerability

**Visual:** 

![1000000135.jpg](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/1000000135.jpg)

---

### Methods Obfuscating TE header

![1000000134.jpg](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/1000000134.jpg)

```jsx
Transfer-Encoding: xchunked

Transfer-Encoding: chunked

Transfer-Encoding: chunked 
Transfer-Encoding: X

Transfer-Encoding:[tab]chunked

[space]Transfer-Encoding: chunked

X: X[\n]Transfer-Encoding: chunked

Transfer-Encoding:
 chunked
```

**Smuggled request content length** 

- Minimum Content needs to be the size of the body of our smuggled request + 1 byte

---

[**TE.CL](http://TE.CL) Bypassing access controls** 

https://m.youtube.com/watch?v=XvqAbDo5DI0&list=PLGb2cDlBWRUX1_7RAIjRkZDYgAB3VbUSw&index=7&pp=iAQB

---

### TE.CL

![Untitled](%5BHTTP%20request%20smuggling%5D%20Methodology%20(1)%2015c29410c99946ab90e16111173841b6/Untitled%208.png)

```jsx
POST / HTTP/1.1
Host: 0ad700a30368234d8192933300730024.web-security-academy.net
Content-Type: application/x-www-form-urlencoded
Content-Length: 4
Transfer-Encoding: chunked

5e
POST /404 HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 14

x=1
0

```