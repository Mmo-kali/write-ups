# [Insecure deserialization] Lab: Modifying serialized objects (1)

---

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled.png)

strange long cookie? 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%201.png)

only is set after logging in… lets pass to decoder. 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%202.png)

decoded with base64 

this is some type of PHP serialization format 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%203.png)

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%204.png)

let change cookie again to administrator : 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%205.png)

this b:0 value seems interesting: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%206.png)

turns out it is a boolean value so right now admin is false lets change that to 1

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%207.png)

after updating our cookie: 

![Untitled](%5BInsecure%20deserialization%5D%20Lab%20Modifying%20serialize%20b36d95a0e70d4ab6a3b7fdeaa60761ae/Untitled%208.png)