# [Insecure deserialization] Lab: Arbitrary object injection in PHP (1)

---

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled.png)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%201.png)

long cookie 

I'm going to run engagement tools to try and gain access to source code with a ‘~’ at beginning of the file names. 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%202.png)

then looking at the site map I discovered: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%203.png)

now look: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%204.png)

some interesting things: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%205.png)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%206.png)

Why did this work, well when the deconstructor is called we can see it is referencing `unlink()` this is a PHP function for deleting files. 

**When is the deconstructor called?** 

- [https://www.php.net/manual/en/language.oop5.decon.php](https://www.php.net/manual/en/language.oop5.decon.php)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%207.png)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Arbitrary%20object%20in%200bf51562a85a4c8f8edcb351defb1d1d/Untitled%208.png)