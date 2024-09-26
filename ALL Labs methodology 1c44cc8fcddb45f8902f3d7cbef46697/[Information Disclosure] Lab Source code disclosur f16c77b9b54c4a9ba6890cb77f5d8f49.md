# [Information Disclosure] Lab: Source code disclosure via backup files (1)

---

This lab is apart of my journey towards my bscp 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled.png)

let's visit the application to get an understanding of its design and functionality. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled%201.png)

Let's use the engagement tool in Burp suite called content discovery to find hidden directories. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled%202.png)

as we can see we found a directory called /backup lets visit it. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled%203.png)

lets go to ProductTemplate

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled%204.png)

access to source code! 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled%205.png)

The first function we see is a function to establish a connection to the DB with the default admin user in Postgres and is the user called ‘postgres’ and his password is hard coded there as well. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Source%20code%20disclosur%20f16c77b9b54c4a9ba6890cb77f5d8f49/Untitled%206.png)

and there we have it lab solved.