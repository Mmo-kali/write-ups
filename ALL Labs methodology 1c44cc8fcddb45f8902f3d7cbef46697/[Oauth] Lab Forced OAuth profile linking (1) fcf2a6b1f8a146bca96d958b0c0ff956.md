# [Oauth]: Lab: Forced OAuth profile linking (1)

---

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled.png)

**Lets find if OAuth is Being used:** 

 ****

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%201.png)

allow users to login with a social media account from another application is a indication that OAuth is being used as a means of access information about the users social media account from the Oauth Service provider and allows client application to query the API for there OpenID and other types of `scope` items. 

**API key after login:** 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%202.png)

Proxy request with Notes: 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%203.png)

OAuth Transaction Start

- Grant type: implicit flow.
    - This means there is no secure back channel for all communication.

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%204.png)

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%205.png)

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%206.png)

---

So when looking at the OAuth flow we Identified a Missing Parameter: `state` 

- This leaves the service vulnerable to CSRF. since the state parameter acts like a CSRF token throughout the OAuth Flow

**Exploit the Missing state parameter to do CSRF to link our own social account to the victim users account.** 

- lets try send the last part of the transaction the API call just to see if it will link the account.

**NOTES:**

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%207.png)

- client_id isn’t being used or stored anywhere.

when logged out and trying login again with social account seems that the clientID is a hardcoded href: 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%208.png)

yea so even after launching a private browser tab the clientID remains the same for a user who isn’t loggedin: 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%209.png)

When trying to resubmit this request: 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%2010.png)

I get this error: 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%2011.png)

**Lets try CSRF with this request:** 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%2012.png)

- the code that is being generated correspond to the series of transaction that just went through and is a way to refer bac kto them with out need to post my social credintials again when click link social account so what if we intercept the generated code and drop the request so we still have a valid code but what we do is send it as a CSRF to the victim it should link our social account to their account.

lets generate CSRF PoC and deliver to victim then logout of our account and lets login in using the social account option. 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%2013.png)

**And Solved:** 

![Untitled](%5BOauth%5D%20Lab%20Forced%20OAuth%20profile%20linking%20(1)%20fcf2a6b1f8a146bca96d958b0c0ff956/Untitled%2014.png)