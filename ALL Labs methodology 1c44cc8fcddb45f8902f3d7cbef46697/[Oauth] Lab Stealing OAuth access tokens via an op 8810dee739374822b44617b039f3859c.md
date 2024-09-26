# [Oauth] Lab: Stealing OAuth access tokens via an open redirect (1)

---

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled.png)

looks like a API call. 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%201.png)

then right after we’re posting our credentials from the API into `/authenticate` 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%202.png)

looks like we have java script in the `/oauthcallback` 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%203.png)

**Full script:** 

```jsx
<script>
const urlSearchParams = new URLSearchParams(window.location.hash.substr(1));
const token = urlSearchParams.get('access_token');
fetch('https://oauth-0ab200810363614e8046790002250032.oauth-server.net/me', {
    method: 'GET',
    headers: {
        'Authorization': 'Bearer ' + token,
        'Content-Type': 'application/json'
    }
})
.then(r => r.json())
.then(j => 
    fetch('/authenticate', {
        method: 'POST',
        headers: {
            'Accept': 'application/json',
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            email: j.email,
            username: j.sub,
            token: token
        })
    }).then(r => document.location = '/'))
</script>
```

looking at redirect_uri: 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%204.png)

one thing I noticed was next post button: 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%205.png)

lets see if this is a open redirect vulnerability: 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%206.png)

Redirected to: 

![Untitled](%5BOauth%5D%20Lab%20Stealing%20OAuth%20access%20tokens%20via%20an%20op%208810dee739374822b44617b039f3859c/Untitled%207.png)