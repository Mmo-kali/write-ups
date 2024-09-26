# [Oauth]: Lab: OAuth account hijacking via redirect_uri (1)

---

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled.png)

**We’re able to change the redirect URI:** 

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%201.png)

result:

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%202.png)

**No `state` or secret parameters to validate input from user:** 

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%203.png)

rather the a CSRF PoC lets just add this request with all query parameters into iframe:

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%204.png)

never mind we will send it as a CSRF PoC: 

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%205.png)

OAuth Callback code from victim: 

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%206.png)

let add code to oAuth callback

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%207.png)

now: 

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%208.png)

**Lab solved:** 

![Untitled](%5BOauth%5D%20Lab%20OAuth%20account%20hijacking%20via%20redirect_u%20ea107a3598db4fa28ceea9b268360364/Untitled%209.png)