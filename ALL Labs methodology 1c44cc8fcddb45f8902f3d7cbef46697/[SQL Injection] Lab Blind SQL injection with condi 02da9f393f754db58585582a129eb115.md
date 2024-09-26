# [SQL Injection] Lab: Blind SQL injection with conditional errors (1)

---

This lab is apart of my journey towards my BSCP. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled.png)

Lets vist the site without a proxy. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%201.png)

lets go to the ‘My account’

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%202.png)

lets try to trigger an error in request. 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%203.png)

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%204.png)

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%205.png)

Password is of length 20 

Using intruder we can get the password with the built in function in ORACLE called Substr: 

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%206.png)

![Untitled](%5BSQL%20Injection%5D%20Lab%20Blind%20SQL%20injection%20with%20condi%2002da9f393f754db58585582a129eb115/Untitled%207.png)