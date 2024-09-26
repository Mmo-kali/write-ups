# [Information Disclosure] Lab: Information disclosure in error messages (1)

---

This lab is a part of my journey towards my BSCP. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%200ee1a7172d184db4a94f5809808ff70b/Untitled.png)

lets first visiting the site with out any proxy on just to understand and map out the application. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%200ee1a7172d184db4a94f5809808ff70b/Untitled%201.png)

as we can see it is a normal shopping application. lets reload the site and look for possible information disclosure in any comments or maybe even the parameter used to select a specific product. 

 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%200ee1a7172d184db4a94f5809808ff70b/Untitled%202.png)

lets change this from a int to a char value see type of error we get. 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%200ee1a7172d184db4a94f5809808ff70b/Untitled%203.png)

and there we have it lab solved: 

![Untitled](%5BInformation%20Disclosure%5D%20Lab%20Information%20disclosur%200ee1a7172d184db4a94f5809808ff70b/Untitled%204.png)