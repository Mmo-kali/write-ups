# [HTTP Host header attacks] Lab: Host header authentication bypass (1)

---

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Host%20header%20authent%203e1e492293004af288339331687d8021/Untitled.png)

when we try access `/admin` 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Host%20header%20authent%203e1e492293004af288339331687d8021/Untitled%201.png)

I need to remove the cookies in the repeater to see the errors: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Host%20header%20authent%203e1e492293004af288339331687d8021/Untitled%202.png)

the host header didn't pass 127.0.0.1 as valid but took `localhost` 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Host%20header%20authent%203e1e492293004af288339331687d8021/Untitled%203.png)

now if we request in browser: 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Host%20header%20authent%203e1e492293004af288339331687d8021/Untitled%204.png)

lab solved 

![Untitled](%5BHTTP%20Host%20header%20attacks%5D%20Lab%20Host%20header%20authent%203e1e492293004af288339331687d8021/Untitled%205.png)