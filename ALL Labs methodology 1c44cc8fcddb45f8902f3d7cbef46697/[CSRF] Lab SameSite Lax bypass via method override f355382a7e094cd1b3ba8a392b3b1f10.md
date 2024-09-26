# [CSRF] Lab: SameSite Lax bypass via method override (1)

---

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled.png)

website is setting a cookie when visiting  `/`  directory, cookie has expires in a day. 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%201.png)

When logging in the site does specify what cookie restriction to use so we can assume by default it is lax. since it is mentioned in lab name but it is adopted by chrome for lax to be the default when no restriction is specified. 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%202.png)

I am going to provide a screen shot of the request for changing the email: 

![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%203.png)

So notice that there is not CSRF protection. 

so we can simply create a csrf poc right? 

**WRONG !!!** 

**Why is it wrong?** 

- Inorder for lax to send a cookie two conditions must be met.
    1. The request uses the `GET` method.
        - The method for changing email is `POST`
    
    1. The request resulted from a top-level navigation by the user, such as clicking on a link.
        - We can accomplish this with a form submit button.

**Satisfy the first condition**

- Lets change the method in the change email request from `POST` to `GET`
    
    
    to change the method to `GET`  we need to provide the email we’re changing in the URL as a query string. 
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%204.png)
    
    but the application only supports `POST` 
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%205.png)
    
    this is a basic CSRF payload when the request is `POST` Notice the cookie isn’t provided. 
    
    so lets looking any weird methods the site is using. 
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%206.png)
    
    These are a few that stood out. 
    
    reading up on the `Sec-Fetch-Site` method we can see: 
    
    - The **Sec-Fetch-Dest** [fetch metadata request header](https://developer.mozilla.org/en-US/docs/Glossary/Fetch_metadata_request_header) signifies the request's *destination*, or where the fetched data will be utilized.
    
    So maybe this is used to control how the site is able to tell the origin of the request. 
    
    so what I'm going to do is send to comparer tool in burp-suite the valid post request that I made when testing the functionality of the site then the invalid post request from my CSRF PoC generated payload to see what is different and what is causing the cookie not to be sent. 
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%207.png)
    
    what if we change the sec-fetch-site value to same-orgin? 
    
    maybe we can overide this method and be able to trick the site into adding the cookie into the request. 
    
    so the only way for us to make this work is by simulating some type of user action. 
    
    so by testing the location.href =/my-account 
    
    then changing the email we can by pass the same origin policy:
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%208.png)
    
    the get request to /my-account
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%209.png)
    
    the POST request for changing email. 
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%2010.png)
    
    i found this site: 
    
    [https://www.sidechannel.blog/en/http-method-override-what-it-is-and-how-a-pentester-can-use-it/](https://www.sidechannel.blog/en/http-method-override-what-it-is-and-how-a-pentester-can-use-it/)
    
    that mentions how we can override the method within a URL using different functions
    
    to add these functions we will need to use `&` after our email query string. 
    
    **Method Override?**
    
    - even thought the request is a GET request we’re overriding it as a POST request.
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%2011.png)
    
    it worked lets generate the CSRF PoC. 
    
    ![Untitled](%5BCSRF%5D%20Lab%20SameSite%20Lax%20bypass%20via%20method%20override%20f355382a7e094cd1b3ba8a392b3b1f10/Untitled%2012.png)
    
    ---
    
    ```jsx
    <html>
      <!-- CSRF PoC - generated by Burp Suite Professional -->
      <body>
        <form action="https://0af4000904c01a7e81a659a800130063.web-security-academy.net/my-account/change-email">
          <input type="hidden" name="email" value="labSolved&#64;t&#46;com" />
          <input type="hidden" name="&#95;method" value="POST" />
          <input type="submit" value="Submit request" />
        </form>
        <script>
          history.pushState('', '', '/');
          document.forms[0].submit();
        </script>
      </body>
    </html>
    
    ```