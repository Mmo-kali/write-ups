---

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/bb71f3dd-eda3-4236-94aa-eae1cad0f66d/Untitled.png)

so lets begin by finding the context. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/7a5c1b4a-9ac1-4619-9874-fe50676094a3/Untitled.png)

**Note:** Whatever we search for is being added to a h1 tag in HTML surrounded by single quotes. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/7b52e0aa-5d55-4a86-9411-1c7a5d2fb7ac/Untitled.png)

not that we know that context let's try to escape the value from the input tag first by giving a random value before the double quotes we will use to flee because is we supply just a double quote we will escape our value without not first being assigned making it difficult for us to look for our reflected result also nothing else will be reflected. 

**NOTE THE PAYLOAD WILL WORK IF NOTHING IS PROVIDED BEFORE THE ESCAPE SEQUENCE< BUT FOR TESTING WE SHOULD INCLUDE A CANARY BEFORE OUR ESCAPSE.** 

 since it is an input tag we will need to use a universal event attribute like onfocus and autofocus to call our alert 

 

so first lets see if double quotes escape and what the application does with the character at the end: 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/b5bdbc78-7c9e-4b9a-88bc-641bbb4a6d39/Untitled.png)

so now we can see we can escape it and inject our own malicious code lets use the onfocus event handler.

this is my payload: 

 note: the double quote at the beginning of alert will be closed by the single quote from the original value attribute. 

```html
lb155" autofocus onfocus="alert(1)
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/0296608f-70fa-4a96-8c6e-4264e689cf83/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/c0f28141-3df3-4884-81fa-7bf011ff6ad9/Untitled.png)

lab solved: 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/caa9a352-83a0-46c9-8a36-c7172e2123b2/Untitled.png)

---

**COMMUNITY SOLUTION:**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2876a1ea-e16e-4e85-a8c7-cd6ef56ad9a2/3b73ae71-a576-41f9-9aab-d99e903a040f/Untitled.png)

this payload required user interaction my payload did not.
