# [Information Disclosure] Lab: Information disclosure on debug page (1)

---

This lab is apart of my journey towards my BSCP cert 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%20bf226e613e614b4bb6ee2da2321336f2/Untitled.png)

SO lets visit the site without a proxy just to map out the functionality and understand the design. 

when going to the site since it is a page that I am looking for I begin using the content discovery tool and configure it to only search for directories not files. to improve the speed a bit instantly I found something that caught my eye was /*cgi-bin* Directory . 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%20bf226e613e614b4bb6ee2da2321336f2/Untitled%201.png)

from here lets go ahead and visit this page 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%20bf226e613e614b4bb6ee2da2321336f2/Untitled%202.png)

lets visit phpinfo.php 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%20bf226e613e614b4bb6ee2da2321336f2/Untitled%203.png)

and there we go lab solved: 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%20bf226e613e614b4bb6ee2da2321336f2/Untitled%204.png)